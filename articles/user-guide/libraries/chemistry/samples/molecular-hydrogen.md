---
title: Ottenere stime dei livelli di energia
description: "Esaminare un programma Q # di esempio che stima i valori del livello di energia dell'idrogeno molecolare."
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276060"
---
# <a name="obtaining-energy-level-estimates"></a>Ottenere stime dei livelli di energia
La stima dei valori dei livelli di energia è una delle principali applicazioni di chimica quantistica. Di seguito viene descritto come eseguire questa operazione per l'esempio canonico di idrogeno molecolare. L'esempio a cui si fa riferimento in questa sezione si trova `MolecularHydrogen` nel repository di esempi di chimica. Un esempio più visivo che traccia l'output è la `MolecularHydrogenGUI` demo.

Il primo passaggio consiste nel costruire l'Hamiltoniana che rappresenta l'idrogeno molecolare. Sebbene possa essere creato tramite lo strumento NWChem, è necessario aggiungere manualmente termini hamiltoniana per brevità in questo esempio.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Per simulare l'hamiltoniana, è necessario convertire gli operatori fermione in operatori qubit. Questa conversione viene eseguita tramite la codifica Giordania-Wigner come indicato di seguito.

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Viene ora passato l'oggetto `qSharpData` che rappresenta l'Hamiltoniana alla `TrotterStepOracle` funzione nella [simulazione di Dynamics hamiltoniana](xref:microsoft.quantum.libraries.standard.algorithms). `TrotterStepOracle`Restituisce un'operazione Quantum che approssima l'evoluzione in tempo reale dell'hamiltoniana.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

È ora possibile usare gli algoritmi di stima della fase della libreria standard per apprendere l'energia dello stato di base usando la simulazione precedente. Questa operazione richiede la preparazione di una corretta approssimazione allo stato di base del quantum. I suggerimenti per tali approssimazioni sono forniti nello `Broombridge` schema, ma in assenza di questi suggerimenti, l'approccio predefinito aggiunge un certo numero di `hamiltonian.NElectrons` elettroni per ridurre al minimo le energie dei termini a un elettrone diagonale. Le funzioni e le operazioni di stima della fase si trovano nello [spazio dei nomi Microsoft. Quantum. characteration](xref:microsoft.quantum.characterization in DocFX notation).

Il frammento di codice seguente mostra in che modo l'output in tempo reale di Evolution dalla libreria di simulazione chimica può essere integrato con la stima della fase quantistica.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

Questo codice Q # può ora essere richiamato dal programma driver. Nell'esempio seguente viene creato un simulatore con stato completo ed eseguito `GetEnergyByTrotterization` per ottenere l'energia dello stato di base.

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Si noti che vengono restituiti due parametri. `energyEst`è la stima dell'energia dello stato di base e dovrebbe essere `-1.137` in media. `phaseEst`è la fase RAW restituita dall'algoritmo di stima della fase ed è utile per la diagnosi quando si verifica un alias a causa di un valore `trotterStep` troppo grande.
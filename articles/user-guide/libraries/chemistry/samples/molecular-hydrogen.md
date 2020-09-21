---
title: Ottenere stime dei livelli di energia
description: Esaminare un Q# programma di esempio per stimare i valori del livello di energia dell'idrogeno molecolare.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759733"
---
# <a name="obtaining-energy-level-estimates"></a>Ottenere stime dei livelli di energia
La stima dei valori dei livelli di energia è una delle principali applicazioni di chimica quantistica. Questo articolo illustra come è possibile eseguire questa operazione per l'esempio canonico di idrogeno molecolare. L'esempio a cui si fa riferimento in questa sezione si trova [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) nel repository di esempi di chimica. Un esempio più visivo che traccia l'output è la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Stima dei valori energetici dell'idrogeno molecolare

Il primo passaggio consiste nel costruire l'Hamiltoniana che rappresenta l'idrogeno molecolare. Sebbene sia possibile costruire questa operazione usando lo strumento NWChem, per brevità, questo esempio aggiunge manualmente i termini hamiltoniana.

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

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Per simulare l'hamiltoniana è necessario convertire gli operatori fermione in operatori qubit. Questa conversione viene eseguita tramite la codifica Giordania-Wigner come indicato di seguito:

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Passare quindi `qSharpData` , che rappresenta l'hamiltoniana, alla `TrotterStepOracle` funzione. `TrotterStepOracle` Restituisce un'operazione Quantum che approssima l'evoluzione in tempo reale dell'hamiltoniana. Per altre informazioni, vedere [simulazione di Dynamics hamiltoniana](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

A questo punto, è possibile usare gli [algoritmi di stima della fase](xref:microsoft.quantum.libraries.characterization) della libreria standard per apprendere l'energia dello stato di base usando la simulazione precedente. Questa operazione richiede la preparazione di una corretta approssimazione allo stato di base del quantum. I suggerimenti per tali approssimazioni sono forniti nello [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema. Tuttavia, in assenza di questi suggerimenti, l'approccio predefinito aggiunge un certo numero di `hamiltonian.NElectrons` elettroni per ridurre al minimo avidamente le energie diagonali a un elettrone. Le funzioni e le funzioni di stima della fase vengono fornite nella notazione DocFX nello spazio dei nomi [Microsoft. Quantum. characteration](xref:microsoft.quantum.characterization) .

Il frammento di codice seguente mostra in che modo l'output di Evolution in tempo reale dalla libreria di simulazione chimica si integra con la stima della fase quantistica.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

È ora possibile richiamare il Q# codice dal programma host. Il codice C# seguente crea un simulatore a stato completo ed esegue `GetEnergyByTrotterization` per ottenere l'energia dello stato di base.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

L'operazione restituisce due parametri: 

- `energyEst` è la stima dell'energia dello stato di base e deve essere vicina alla `-1.137` Media. 
- `phaseEst` è la fase RAW restituita dall'algoritmo di stima della fase. Questa operazione è utile per la diagnosi degli alias quando si verifica a causa di un `trotterStep` valore troppo grande.

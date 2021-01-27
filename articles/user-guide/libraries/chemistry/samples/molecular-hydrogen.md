---
title: Ottenere stime dei livelli di energia
description: Esaminare un Q# programma di esempio per stimare i valori del livello di energia dell'idrogeno molecolare.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 60935e7c1e8c674fab3a546c1f110f589d2e6b77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855047"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="ef70c-103">Ottenere stime dei livelli di energia</span><span class="sxs-lookup"><span data-stu-id="ef70c-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="ef70c-104">La stima dei valori dei livelli di energia è una delle principali applicazioni di chimica quantistica.</span><span class="sxs-lookup"><span data-stu-id="ef70c-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="ef70c-105">Questo articolo illustra come è possibile eseguire questa operazione per l'esempio canonico di idrogeno molecolare.</span><span class="sxs-lookup"><span data-stu-id="ef70c-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="ef70c-106">L'esempio a cui si fa riferimento in questa sezione si trova [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) nel repository di esempi di chimica.</span><span class="sxs-lookup"><span data-stu-id="ef70c-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="ef70c-107">Un esempio più visivo che traccia l'output è la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span><span class="sxs-lookup"><span data-stu-id="ef70c-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="ef70c-108">Stima dei valori energetici dell'idrogeno molecolare</span><span class="sxs-lookup"><span data-stu-id="ef70c-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="ef70c-109">Il primo passaggio consiste nel costruire l'Hamiltoniana che rappresenta l'idrogeno molecolare.</span><span class="sxs-lookup"><span data-stu-id="ef70c-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="ef70c-110">Sebbene sia possibile costruire questa operazione usando lo strumento NWChem, per brevità, questo esempio aggiunge manualmente i termini hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="ef70c-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="ef70c-111">Per simulare l'hamiltoniana è necessario convertire gli operatori fermione in operatori qubit.</span><span class="sxs-lookup"><span data-stu-id="ef70c-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="ef70c-112">Questa conversione viene eseguita tramite la codifica Jordan-Wigner come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef70c-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="ef70c-113">Passare quindi `qSharpData` , che rappresenta l'hamiltoniana, alla `TrotterStepOracle` funzione.</span><span class="sxs-lookup"><span data-stu-id="ef70c-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="ef70c-114">`TrotterStepOracle` Restituisce un'operazione Quantum che approssima l'evoluzione in tempo reale dell'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="ef70c-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="ef70c-115">Per altre informazioni, vedere [simulazione di Dynamics hamiltoniana](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="ef70c-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="ef70c-116">A questo punto, è possibile usare gli [algoritmi di stima della fase](xref:microsoft.quantum.libraries.characterization) della libreria standard per apprendere l'energia dello stato di base usando la simulazione precedente.</span><span class="sxs-lookup"><span data-stu-id="ef70c-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="ef70c-117">Questa operazione richiede la preparazione di una corretta approssimazione allo stato di base del quantum.</span><span class="sxs-lookup"><span data-stu-id="ef70c-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="ef70c-118">I suggerimenti per tali approssimazioni sono forniti nello [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span><span class="sxs-lookup"><span data-stu-id="ef70c-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="ef70c-119">Tuttavia, in assenza di questi suggerimenti, l'approccio predefinito aggiunge un certo numero di `hamiltonian.NElectrons` elettroni per ridurre al minimo avidamente le energie diagonali a un elettrone.</span><span class="sxs-lookup"><span data-stu-id="ef70c-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="ef70c-120">Le funzioni e le funzioni di stima della fase vengono fornite nella notazione DocFX nello spazio dei nomi [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization) .</span><span class="sxs-lookup"><span data-stu-id="ef70c-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="ef70c-121">Il frammento di codice seguente mostra in che modo l'output di Evolution in tempo reale dalla libreria di simulazione chimica si integra con la stima della fase quantistica.</span><span class="sxs-lookup"><span data-stu-id="ef70c-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="ef70c-122">È ora possibile richiamare il Q# codice dal programma host.</span><span class="sxs-lookup"><span data-stu-id="ef70c-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="ef70c-123">Il codice C# seguente crea un simulatore a stato completo ed esegue `GetEnergyByTrotterization` per ottenere l'energia dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="ef70c-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="ef70c-124">L'operazione restituisce due parametri:</span><span class="sxs-lookup"><span data-stu-id="ef70c-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="ef70c-125">`energyEst` è la stima dell'energia dello stato di base e deve essere vicina alla `-1.137` Media.</span><span class="sxs-lookup"><span data-stu-id="ef70c-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="ef70c-126">`phaseEst` è la fase RAW restituita dall'algoritmo di stima della fase.</span><span class="sxs-lookup"><span data-stu-id="ef70c-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="ef70c-127">Questa operazione è utile per la diagnosi degli alias quando si verifica a causa di un `trotterStep` valore troppo grande.</span><span class="sxs-lookup"><span data-stu-id="ef70c-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>

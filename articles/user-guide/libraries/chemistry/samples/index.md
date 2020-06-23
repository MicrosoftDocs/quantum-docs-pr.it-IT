---
title: Applicazioni di esempio di chimica quantistica
description: Esplorare le applicazioni di esempio della libreria di chimica quantistica Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273617"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="e7434-103">Esempi di chimica quantistica</span><span class="sxs-lookup"><span data-stu-id="e7434-103">Quantum chemistry examples</span></span>

<span data-ttu-id="e7434-104">Nei concetti di chimica quantistica sono state create manualmente le hamiltoniane di particelle fermioniche di esempio.</span><span class="sxs-lookup"><span data-stu-id="e7434-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="e7434-105">Gli algoritmi di simulazione chimica descritti in [Simulazione della dinamica hamiltoniana](xref:microsoft.quantum.libraries.standard.algorithms) verranno ora combinati con la [stima della fase quantistica](xref:microsoft.quantum.libraries.characterization) nella libreria canonica.</span><span class="sxs-lookup"><span data-stu-id="e7434-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="e7434-106">Questa combinazione permette di ottenere stime dei livelli di energia nella molecola rappresentata e questa costituisce una delle applicazioni chiave della chimica quantistica in un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="e7434-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="e7434-107">Invece di specificare i termini dell'hamiltoniana uno alla volta, verranno usati alcuni esempi che consentono di eseguire esperimenti di chimica quantistica su larga scala.</span><span class="sxs-lookup"><span data-stu-id="e7434-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="e7434-108">Si inizierà con esempi che caricano un'hamiltoniana chimica codificata nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="e7434-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="e7434-109">Per le molecole che sono troppo grandi per la simulazione nel [simulatore di stati completo](xref:microsoft.quantum.machines.full-state-simulator), è comunque possibile eseguire interessanti esperimenti scientifici.</span><span class="sxs-lookup"><span data-stu-id="e7434-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="e7434-110">È ad esempio possibile valutare comunque i costi di simulazioni chimiche di grandi dimensioni in termini di risorse impostando come destinazione il [simulatore di tracce](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="e7434-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="e7434-111">A questo punto verranno usati alcuni degli esempi forniti per illustrare le interessanti applicazioni della libreria di simulazione chimica.</span><span class="sxs-lookup"><span data-stu-id="e7434-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>

---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Tipo definito dall'utente SimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 2f340492b51c97e353cc071d6d563a30a1db86d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192435"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="86cf6-102">Tipo definito dall'utente SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="86cf6-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="86cf6-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="86cf6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="86cf6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86cf6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86cf6-105">Rappresenta un algoritmo di simulazione indipendente dal tempo.</span><span class="sxs-lookup"><span data-stu-id="86cf6-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="86cf6-106">Una tecnica di simulazione indipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="86cf6-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="86cf6-107">per l'evoluzione dell'ora unitaria per un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="86cf6-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```


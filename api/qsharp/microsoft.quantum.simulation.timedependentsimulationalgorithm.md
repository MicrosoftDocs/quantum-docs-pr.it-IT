---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Tipo definito dall'utente TimeDependentSimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192520"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="7e7f1-102">Tipo definito dall'utente TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="7e7f1-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="7e7f1-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7e7f1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7e7f1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e7f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e7f1-105">Rappresenta un algoritmo di simulazione dipendente dal tempo.</span><span class="sxs-lookup"><span data-stu-id="7e7f1-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="7e7f1-106">Una tecnica di simulazione dipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="7e7f1-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="7e7f1-107">per l'evoluzione del tempo unitario per un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7e7f1-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```


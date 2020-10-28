---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Tipo definito dall'utente TimeDependentSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725753"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="afc5d-102">Tipo definito dall'utente TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="afc5d-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="afc5d-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="afc5d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="afc5d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afc5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afc5d-105">Rappresenta un algoritmo di simulazione dipendente dal tempo.</span><span class="sxs-lookup"><span data-stu-id="afc5d-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="afc5d-106">Una tecnica di simulazione dipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="afc5d-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="afc5d-107">per l'evoluzione del tempo unitario per un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="afc5d-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```


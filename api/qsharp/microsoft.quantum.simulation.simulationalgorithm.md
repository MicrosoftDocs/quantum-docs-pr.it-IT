---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Tipo definito dall'utente SimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725571"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="b5c2f-102">Tipo definito dall'utente SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b5c2f-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="b5c2f-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b5c2f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b5c2f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5c2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5c2f-105">Rappresenta un algoritmo di simulazione indipendente dal tempo.</span><span class="sxs-lookup"><span data-stu-id="b5c2f-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="b5c2f-106">Una tecnica di simulazione indipendente dal tempo converte un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="b5c2f-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="b5c2f-107">per l'evoluzione dell'ora unitaria per un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b5c2f-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```


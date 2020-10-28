---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Tipo definito dall'utente EvolutionUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724857"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="2070d-102">Tipo definito dall'utente EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="2070d-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="2070d-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2070d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2070d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2070d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2070d-105">Rappresenta un operatore di evoluzione temporale unitario.</span><span class="sxs-lookup"><span data-stu-id="2070d-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="2070d-106">Il primo parametro è la durata di Time-Evolution e il secondo parametro è il registro qubit eseguito dall'unità.</span><span class="sxs-lookup"><span data-stu-id="2070d-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```


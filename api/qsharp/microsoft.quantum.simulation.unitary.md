---
uid: Microsoft.Quantum.Simulation.Unitary
title: Tipo definito dall'utente unitario
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725333"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="e2ce0-102">Tipo definito dall'utente unitario</span><span class="sxs-lookup"><span data-stu-id="e2ce0-102">Unitary user defined type</span></span>

<span data-ttu-id="e2ce0-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e2ce0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e2ce0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2ce0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2ce0-105">Rappresenta l'evoluzione in un operatore unitario.</span><span class="sxs-lookup"><span data-stu-id="e2ce0-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```


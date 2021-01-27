---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definito dall'utente DiscreteOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842565"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="9b0c9-102">Tipo definito dall'utente DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="9b0c9-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="9b0c9-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9b0c9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9b0c9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b0c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b0c9-105">Rappresenta un Oracle a tempo discreto.</span><span class="sxs-lookup"><span data-stu-id="9b0c9-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="9b0c9-106">Si tratta di un Oracle che implementa $U ^ m $ per un'operazione fissa $U $ e un numero intero non negativo $m $.</span><span class="sxs-lookup"><span data-stu-id="9b0c9-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```


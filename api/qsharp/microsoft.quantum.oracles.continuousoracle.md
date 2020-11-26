---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Tipo definito dall'utente ContinuousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226792"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="ec4b6-102">Tipo definito dall'utente ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="ec4b6-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="ec4b6-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ec4b6-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ec4b6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec4b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec4b6-105">Rappresenta un Oracle a tempo continuo.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="ec4b6-106">Si tratta di un Oracle che implementa $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ per tutti gli orari $t $, in cui $U $ è un'operazione fissa e dove $ \delta t $ è un numero reale non negativo.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```


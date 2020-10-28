---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Tipo definito dall'utente ContinuousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724314"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="7980b-102">Tipo definito dall'utente ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="7980b-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="7980b-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="7980b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="7980b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7980b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7980b-105">Rappresenta un Oracle a tempo continuo.</span><span class="sxs-lookup"><span data-stu-id="7980b-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="7980b-106">Si tratta di un Oracle che implementa $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ per tutti gli orari $t $, in cui $U $ è un'operazione fissa e dove $ \delta t $ è un numero reale non negativo.</span><span class="sxs-lookup"><span data-stu-id="7980b-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```


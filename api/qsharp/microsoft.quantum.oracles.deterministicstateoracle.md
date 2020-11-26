---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definito dall'utente DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193931"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="9fec7-102">Tipo definito dall'utente DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="9fec7-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="9fec7-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9fec7-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9fec7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fec7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fec7-105">Rappresenta un oggetto Oracle per la preparazione dello stato deterministico.</span><span class="sxs-lookup"><span data-stu-id="9fec7-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="9fec7-106">L'input per Oracle $O $ è:</span><span class="sxs-lookup"><span data-stu-id="9fec7-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="9fec7-107">Registro in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="9fec7-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="9fec7-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9fec7-108">Remarks</span></span>

<span data-ttu-id="9fec7-109">Questo Oracle definito da $O \ket {0} = \ket{\psi} $ agisce sullo stato di base di calcolo $ \ket {0} $ per creare lo stato $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9fec7-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="9fec7-110">Il primo parametro è il registro qubit di $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9fec7-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>
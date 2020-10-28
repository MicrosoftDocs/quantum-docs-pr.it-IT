---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definito dall'utente ObliviousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710993"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="03125-102">Tipo definito dall'utente ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="03125-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="03125-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="03125-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="03125-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03125-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03125-105">Rappresenta un Oracle per l'amplificazione dell'ampiezza ignari.</span><span class="sxs-lookup"><span data-stu-id="03125-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="03125-106">Gli input per Oracle $O $ sono:</span><span class="sxs-lookup"><span data-stu-id="03125-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="03125-107">Il registro ancilla $a $ su cui $O $ agisce.</span><span class="sxs-lookup"><span data-stu-id="03125-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="03125-108">Il registro di sistema $s $ sul quale viene applicato il gruppo di $U $ desiderato, dopo aver selezionato il registro $a $ in stato $ \ket{t} $ \_ .</span><span class="sxs-lookup"><span data-stu-id="03125-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="03125-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="03125-109">Remarks</span></span>

<span data-ttu-id="03125-110">Questo Oracle definito da $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agisce sullo stato ancilla $ \ket{s} a \_ $ per implementare l'unità $U $ su qualsiasi stato del sistema $ \ket{\psi} \_ s $ con l'ampiezza $ \lambda $ nella base contrassegnata da $ \ket{t} $ \_ .</span><span class="sxs-lookup"><span data-stu-id="03125-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="03125-111">Il primo parametro è il registro qubit di $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="03125-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="03125-112">Il secondo parametro è il registro qubit di $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="03125-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>
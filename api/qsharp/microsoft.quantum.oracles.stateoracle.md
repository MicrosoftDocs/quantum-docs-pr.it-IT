---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definito dall'utente StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226605"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="4be10-102">Tipo definito dall'utente StateOracle</span><span class="sxs-lookup"><span data-stu-id="4be10-102">StateOracle user defined type</span></span>

<span data-ttu-id="4be10-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4be10-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4be10-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4be10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4be10-105">Rappresenta un oggetto Oracle per la preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="4be10-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="4be10-106">Gli input per Oracle $O $ sono:</span><span class="sxs-lookup"><span data-stu-id="4be10-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="4be10-107">Intero che indicizza il flag qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="4be10-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="4be10-108">Il registro di sistema $s $ in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="4be10-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="4be10-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="4be10-109">Remarks</span></span>

<span data-ttu-id="4be10-110">Questo Oracle definito da $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agisce sullo stato di base di calcolo $ \ket {0} \_ {f} \ket {0} \_ s $ per creare lo stato di destinazione $ \ket{\psi} \_ s $ con l'ampiezza $ \lambda $ nella base contrassegnata da $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="4be10-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="4be10-111">Il primo parametro è un indice del registro qubit di $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="4be10-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="4be10-112">Il secondo parametro include entrambi i registri.</span><span class="sxs-lookup"><span data-stu-id="4be10-112">The second parameter encompassed both registers.</span></span>
---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definito dall'utente StateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854474"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="b57d4-102">Tipo definito dall'utente StateOracle</span><span class="sxs-lookup"><span data-stu-id="b57d4-102">StateOracle user defined type</span></span>

<span data-ttu-id="b57d4-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b57d4-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b57d4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b57d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b57d4-105">Rappresenta un oggetto Oracle per la preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="b57d4-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="b57d4-106">Gli input per Oracle $O $ sono:</span><span class="sxs-lookup"><span data-stu-id="b57d4-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="b57d4-107">Intero che indicizza il flag qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="b57d4-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="b57d4-108">Il registro di sistema $s $ in cui viene archiviato lo stato quantum desiderato $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="b57d4-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="b57d4-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="b57d4-109">Remarks</span></span>

<span data-ttu-id="b57d4-110">Questo Oracle definito da $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agisce sullo stato di base di calcolo $ \ket {0} \_ {f} \ket {0} \_ s $ per creare lo stato di destinazione $ \ket{\psi} \_ s $ con l'ampiezza $ \lambda $ nella base contrassegnata da $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="b57d4-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="b57d4-111">Il primo parametro è un indice del registro qubit di $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="b57d4-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="b57d4-112">Il secondo parametro include entrambi i registri.</span><span class="sxs-lookup"><span data-stu-id="b57d4-112">The second parameter encompassed both registers.</span></span>
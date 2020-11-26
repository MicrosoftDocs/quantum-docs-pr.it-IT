---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204641"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="2219f-102">UncurriedOp (funzione)</span><span class="sxs-lookup"><span data-stu-id="2219f-102">UncurriedOp function</span></span>

<span data-ttu-id="2219f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2219f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2219f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2219f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2219f-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="2219f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="2219f-106">Input</span><span class="sxs-lookup"><span data-stu-id="2219f-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="2219f-107">curriedOp: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2219f-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2219f-108">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="2219f-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="2219f-109">Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2219f-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2219f-110">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="2219f-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2219f-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2219f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2219f-112">T</span><span class="sxs-lookup"><span data-stu-id="2219f-112">'T</span></span>

<span data-ttu-id="2219f-113">Tipo del primo input di un'operazione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="2219f-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="2219f-114">' U</span><span class="sxs-lookup"><span data-stu-id="2219f-114">'U</span></span>

<span data-ttu-id="2219f-115">Tipo del secondo input di un'operazione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="2219f-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="2219f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2219f-116">See Also</span></span>

- [<span data-ttu-id="2219f-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="2219f-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="2219f-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="2219f-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="2219f-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="2219f-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)
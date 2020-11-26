---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204624"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="e6ab7-102">UncurriedOpA (funzione)</span><span class="sxs-lookup"><span data-stu-id="e6ab7-102">UncurriedOpA function</span></span>

<span data-ttu-id="e6ab7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6ab7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6ab7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6ab7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6ab7-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="e6ab7-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="e6ab7-106">Il modificatore `A` indica che le operazioni sono adjointable.</span><span class="sxs-lookup"><span data-stu-id="e6ab7-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="e6ab7-107">Input</span><span class="sxs-lookup"><span data-stu-id="e6ab7-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="e6ab7-108">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e6ab7-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e6ab7-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="e6ab7-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="e6ab7-110">Output: (' t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e6ab7-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e6ab7-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="e6ab7-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6ab7-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e6ab7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6ab7-113">T</span><span class="sxs-lookup"><span data-stu-id="e6ab7-113">'T</span></span>

<span data-ttu-id="e6ab7-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="e6ab7-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="e6ab7-115">' U</span><span class="sxs-lookup"><span data-stu-id="e6ab7-115">'U</span></span>

<span data-ttu-id="e6ab7-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="e6ab7-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6ab7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6ab7-117">See Also</span></span>

- [<span data-ttu-id="e6ab7-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="e6ab7-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
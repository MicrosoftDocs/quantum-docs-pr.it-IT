---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216388"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="c7ad0-102">UncurriedOpCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="c7ad0-102">UncurriedOpCA function</span></span>

<span data-ttu-id="c7ad0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7ad0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7ad0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7ad0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7ad0-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="c7ad0-106">Il modificatore `CA` indica che le operazioni sono controllabili e adjointable.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="c7ad0-107">Input</span><span class="sxs-lookup"><span data-stu-id="c7ad0-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="c7ad0-108">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c7ad0-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c7ad0-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="c7ad0-110">Output: (' t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c7ad0-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c7ad0-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="c7ad0-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c7ad0-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c7ad0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7ad0-113">T</span><span class="sxs-lookup"><span data-stu-id="c7ad0-113">'T</span></span>

<span data-ttu-id="c7ad0-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="c7ad0-115">' U</span><span class="sxs-lookup"><span data-stu-id="c7ad0-115">'U</span></span>

<span data-ttu-id="c7ad0-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ad0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ad0-117">See Also</span></span>

- [<span data-ttu-id="c7ad0-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="c7ad0-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
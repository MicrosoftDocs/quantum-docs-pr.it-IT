---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204590"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="87b1c-102">UncurriedOpC (funzione)</span><span class="sxs-lookup"><span data-stu-id="87b1c-102">UncurriedOpC function</span></span>

<span data-ttu-id="87b1c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87b1c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87b1c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87b1c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87b1c-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="87b1c-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="87b1c-106">Il modificatore `C` indica che le operazioni sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="87b1c-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="87b1c-107">Input</span><span class="sxs-lookup"><span data-stu-id="87b1c-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="87b1c-108">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="87b1c-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="87b1c-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="87b1c-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="87b1c-110">Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="87b1c-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="87b1c-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="87b1c-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="87b1c-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="87b1c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87b1c-113">T</span><span class="sxs-lookup"><span data-stu-id="87b1c-113">'T</span></span>

<span data-ttu-id="87b1c-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="87b1c-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="87b1c-115">' U</span><span class="sxs-lookup"><span data-stu-id="87b1c-115">'U</span></span>

<span data-ttu-id="87b1c-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="87b1c-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="87b1c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b1c-117">See Also</span></span>

- [<span data-ttu-id="87b1c-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="87b1c-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851981"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="3cb2a-102">UncurriedOpC (funzione)</span><span class="sxs-lookup"><span data-stu-id="3cb2a-102">UncurriedOpC function</span></span>

<span data-ttu-id="3cb2a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3cb2a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3cb2a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3cb2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3cb2a-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="3cb2a-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="3cb2a-106">Il modificatore `C` indica che le operazioni sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="3cb2a-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="3cb2a-107">Input</span><span class="sxs-lookup"><span data-stu-id="3cb2a-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="3cb2a-108">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="3cb2a-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3cb2a-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="3cb2a-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="3cb2a-110">Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="3cb2a-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3cb2a-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="3cb2a-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3cb2a-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3cb2a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3cb2a-113">T</span><span class="sxs-lookup"><span data-stu-id="3cb2a-113">'T</span></span>

<span data-ttu-id="3cb2a-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="3cb2a-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="3cb2a-115">' U</span><span class="sxs-lookup"><span data-stu-id="3cb2a-115">'U</span></span>

<span data-ttu-id="3cb2a-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="3cb2a-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cb2a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cb2a-117">See Also</span></span>

- [<span data-ttu-id="3cb2a-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="3cb2a-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715221"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="4cb93-102">UncurriedOpA (funzione)</span><span class="sxs-lookup"><span data-stu-id="4cb93-102">UncurriedOpA function</span></span>

<span data-ttu-id="4cb93-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4cb93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4cb93-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4cb93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4cb93-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="4cb93-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="4cb93-106">Il modificatore `A` indica che le operazioni sono adjointable.</span><span class="sxs-lookup"><span data-stu-id="4cb93-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="4cb93-107">Input</span><span class="sxs-lookup"><span data-stu-id="4cb93-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="4cb93-108">curriedOp:' t->' U => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cb93-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4cb93-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="4cb93-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="4cb93-110">Output: (t,' U) => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cb93-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4cb93-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="4cb93-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4cb93-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4cb93-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4cb93-113">T</span><span class="sxs-lookup"><span data-stu-id="4cb93-113">'T</span></span>

<span data-ttu-id="4cb93-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="4cb93-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="4cb93-115">' U</span><span class="sxs-lookup"><span data-stu-id="4cb93-115">'U</span></span>

<span data-ttu-id="4cb93-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="4cb93-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cb93-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cb93-117">See Also</span></span>

- [<span data-ttu-id="4cb93-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="4cb93-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
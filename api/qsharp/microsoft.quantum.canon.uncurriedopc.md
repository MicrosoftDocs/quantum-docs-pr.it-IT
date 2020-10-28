---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715210"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="a5d48-102">UncurriedOpC (funzione)</span><span class="sxs-lookup"><span data-stu-id="a5d48-102">UncurriedOpC function</span></span>

<span data-ttu-id="a5d48-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5d48-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5d48-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5d48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5d48-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="a5d48-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="a5d48-106">Il modificatore `C` indica che le operazioni sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="a5d48-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a5d48-107">Input</span><span class="sxs-lookup"><span data-stu-id="a5d48-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="a5d48-108">curriedOp: t->' U => [unità](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="a5d48-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a5d48-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="a5d48-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="a5d48-110">Output: (t,' U) => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5d48-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a5d48-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="a5d48-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5d48-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a5d48-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5d48-113">T</span><span class="sxs-lookup"><span data-stu-id="a5d48-113">'T</span></span>

<span data-ttu-id="a5d48-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="a5d48-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="a5d48-115">' U</span><span class="sxs-lookup"><span data-stu-id="a5d48-115">'U</span></span>

<span data-ttu-id="a5d48-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="a5d48-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5d48-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5d48-117">See Also</span></span>

- [<span data-ttu-id="a5d48-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="a5d48-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
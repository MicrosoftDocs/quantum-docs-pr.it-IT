---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715207"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="cf9a5-102">UncurriedOpCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="cf9a5-102">UncurriedOpCA function</span></span>

<span data-ttu-id="cf9a5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf9a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf9a5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf9a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf9a5-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="cf9a5-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="cf9a5-106">Il modificatore `CA` indica che le operazioni sono controllabili e adjointable.</span><span class="sxs-lookup"><span data-stu-id="cf9a5-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="cf9a5-107">Input</span><span class="sxs-lookup"><span data-stu-id="cf9a5-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="cf9a5-108">curriedOp: t->' U => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="cf9a5-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="cf9a5-109">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="cf9a5-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="cf9a5-110">Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="cf9a5-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="cf9a5-111">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="cf9a5-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cf9a5-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="cf9a5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf9a5-113">T</span><span class="sxs-lookup"><span data-stu-id="cf9a5-113">'T</span></span>

<span data-ttu-id="cf9a5-114">Tipo del primo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="cf9a5-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="cf9a5-115">' U</span><span class="sxs-lookup"><span data-stu-id="cf9a5-115">'U</span></span>

<span data-ttu-id="cf9a5-116">Tipo del secondo argomento di una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="cf9a5-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf9a5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf9a5-117">See Also</span></span>

- [<span data-ttu-id="cf9a5-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="cf9a5-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)
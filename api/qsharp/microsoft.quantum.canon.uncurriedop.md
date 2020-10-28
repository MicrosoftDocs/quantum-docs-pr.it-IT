---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715238"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="7465d-102">UncurriedOp (funzione)</span><span class="sxs-lookup"><span data-stu-id="7465d-102">UncurriedOp function</span></span>

<span data-ttu-id="7465d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7465d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7465d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7465d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7465d-105">Data una funzione che restituisce le operazioni, restituisce una nuova operazione che accetta entrambi gli input come tupla.</span><span class="sxs-lookup"><span data-stu-id="7465d-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="7465d-106">Input</span><span class="sxs-lookup"><span data-stu-id="7465d-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="7465d-107">curriedOp: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7465d-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7465d-108">Funzione che restituisce le operazioni.</span><span class="sxs-lookup"><span data-stu-id="7465d-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="7465d-109">Output: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7465d-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7465d-110">Nuova operazione `op` che `op(t, u)` equivale a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="7465d-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7465d-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7465d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7465d-112">T</span><span class="sxs-lookup"><span data-stu-id="7465d-112">'T</span></span>

<span data-ttu-id="7465d-113">Tipo del primo input di un'operazione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="7465d-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="7465d-114">' U</span><span class="sxs-lookup"><span data-stu-id="7465d-114">'U</span></span>

<span data-ttu-id="7465d-115">Tipo del secondo input di un'operazione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="7465d-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7465d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7465d-116">See Also</span></span>

- [<span data-ttu-id="7465d-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="7465d-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="7465d-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="7465d-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="7465d-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="7465d-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)
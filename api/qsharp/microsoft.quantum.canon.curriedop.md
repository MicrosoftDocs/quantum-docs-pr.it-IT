---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216626"
---
# <a name="curriedop-function"></a><span data-ttu-id="72212-102">CurriedOp (funzione)</span><span class="sxs-lookup"><span data-stu-id="72212-102">CurriedOp function</span></span>

<span data-ttu-id="72212-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72212-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72212-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72212-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72212-105">Restituisce una versione sottoposta a currying di un'operazione su due input.</span><span class="sxs-lookup"><span data-stu-id="72212-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="72212-106">In altre condizioni, data un'operazione con due input, questa funzione applica la $f isomorfismo (x, y) \equiv f (x) (y) di curry per restituire un'operazione di un input che restituisce un'operazione di un input.</span><span class="sxs-lookup"><span data-stu-id="72212-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="72212-107">Input</span><span class="sxs-lookup"><span data-stu-id="72212-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="72212-108">op: (t,' U) => [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72212-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="72212-109">Operazione il cui input è una coppia.</span><span class="sxs-lookup"><span data-stu-id="72212-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="72212-110">Output: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72212-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="72212-111">Operazione che accetta il primo elemento di una coppia e restituisce un'operazione che accetta come input il secondo elemento dell'input dell'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="72212-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="72212-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="72212-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72212-113">T</span><span class="sxs-lookup"><span data-stu-id="72212-113">'T</span></span>

<span data-ttu-id="72212-114">Tipo del primo componente di una funzione definita per le coppie.</span><span class="sxs-lookup"><span data-stu-id="72212-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="72212-115">' U</span><span class="sxs-lookup"><span data-stu-id="72212-115">'U</span></span>

<span data-ttu-id="72212-116">Tipo del secondo componente di una funzione definita per le coppie.</span><span class="sxs-lookup"><span data-stu-id="72212-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="72212-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="72212-117">Remarks</span></span>

<span data-ttu-id="72212-118">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="72212-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```
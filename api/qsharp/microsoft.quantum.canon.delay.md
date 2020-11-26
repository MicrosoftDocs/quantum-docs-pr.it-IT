---
uid: Microsoft.Quantum.Canon.Delay
title: Operazione Delay
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216507"
---
# <a name="delay-operation"></a><span data-ttu-id="5318a-102">Operazione Delay</span><span class="sxs-lookup"><span data-stu-id="5318a-102">Delay operation</span></span>

<span data-ttu-id="5318a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5318a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5318a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5318a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5318a-105">Applica una determinata operazione con un ritardo.</span><span class="sxs-lookup"><span data-stu-id="5318a-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="5318a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5318a-106">Description</span></span>

<span data-ttu-id="5318a-107">Data un'operazione e un input per tale operazione, applica l'operazione dopo che è stato fornito un input aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5318a-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="5318a-108">In particolare, l'espressione `Delay(op, arg, _)` è un'operazione che si applica `op` a `arg` quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="5318a-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="5318a-109">Expression `Delay(op,arg,_)` consente di ritardare l'applicazione di `op` .</span><span class="sxs-lookup"><span data-stu-id="5318a-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="5318a-110">Input</span><span class="sxs-lookup"><span data-stu-id="5318a-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="5318a-111">op:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="5318a-111">op : 'T => 'U</span></span> 

<span data-ttu-id="5318a-112">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="5318a-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="5318a-113">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="5318a-113">arg : 'T</span></span>

<span data-ttu-id="5318a-114">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5318a-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="5318a-115">Aux: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5318a-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="5318a-116">Argomento utilizzato per ritardare l'applicazione dell'operazione utilizzando l'applicazione parziale.</span><span class="sxs-lookup"><span data-stu-id="5318a-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="5318a-117">Output:' U</span><span class="sxs-lookup"><span data-stu-id="5318a-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5318a-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5318a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5318a-119">T</span><span class="sxs-lookup"><span data-stu-id="5318a-119">'T</span></span>

<span data-ttu-id="5318a-120">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="5318a-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="5318a-121">' U</span><span class="sxs-lookup"><span data-stu-id="5318a-121">'U</span></span>

<span data-ttu-id="5318a-122">Tipo restituito dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="5318a-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="5318a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5318a-123">See Also</span></span>

- [<span data-ttu-id="5318a-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="5318a-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="5318a-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="5318a-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="5318a-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="5318a-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="5318a-127">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="5318a-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
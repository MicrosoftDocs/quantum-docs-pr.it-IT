---
uid: Microsoft.Quantum.Canon.DelayC
title: Operazione DelayC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216490"
---
# <a name="delayc-operation"></a><span data-ttu-id="8d001-102">Operazione DelayC</span><span class="sxs-lookup"><span data-stu-id="8d001-102">DelayC operation</span></span>

<span data-ttu-id="8d001-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d001-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d001-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d001-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d001-105">Applica una determinata operazione con un ritardo.</span><span class="sxs-lookup"><span data-stu-id="8d001-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8d001-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d001-106">Description</span></span>

<span data-ttu-id="8d001-107">Data un'operazione e un input per tale operazione, applica l'operazione dopo che è stato fornito un input aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8d001-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="8d001-108">In particolare, l'espressione `Delay(op, arg, _)` è un'operazione che si applica `op` a `arg` quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="8d001-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="8d001-109">Expression `Delay(op,arg,_)` consente di ritardare l'applicazione di `op` .</span><span class="sxs-lookup"><span data-stu-id="8d001-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="8d001-110">Input</span><span class="sxs-lookup"><span data-stu-id="8d001-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8d001-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="8d001-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8d001-112">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="8d001-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="8d001-113">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="8d001-113">arg : 'T</span></span>

<span data-ttu-id="8d001-114">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8d001-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="8d001-115">Aux: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d001-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="8d001-116">Argomento utilizzato per ritardare l'applicazione dell'operazione utilizzando l'applicazione parziale.</span><span class="sxs-lookup"><span data-stu-id="8d001-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d001-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d001-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8d001-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8d001-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8d001-119">T</span><span class="sxs-lookup"><span data-stu-id="8d001-119">'T</span></span>

<span data-ttu-id="8d001-120">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="8d001-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d001-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d001-121">See Also</span></span>

- [<span data-ttu-id="8d001-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="8d001-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="8d001-123">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="8d001-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
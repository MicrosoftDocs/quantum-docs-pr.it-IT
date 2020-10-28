---
uid: Microsoft.Quantum.Canon.DelayA
title: Operazione delaya
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716299"
---
# <a name="delaya-operation"></a><span data-ttu-id="a7b7a-102">Operazione delaya</span><span class="sxs-lookup"><span data-stu-id="a7b7a-102">DelayA operation</span></span>

<span data-ttu-id="a7b7a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7b7a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7b7a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7b7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7b7a-105">Applica una determinata operazione con un ritardo.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="a7b7a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7b7a-106">Description</span></span>

<span data-ttu-id="a7b7a-107">Data un'operazione e un input per tale operazione, applica l'operazione dopo che è stato fornito un input aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="a7b7a-108">In particolare, l'espressione `Delay(op, arg, _)` è un'operazione che si applica `op` a `arg` quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="a7b7a-109">Expression `Delay(op,arg,_)` consente di ritardare l'applicazione di `op` .</span><span class="sxs-lookup"><span data-stu-id="a7b7a-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="a7b7a-110">Input</span><span class="sxs-lookup"><span data-stu-id="a7b7a-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="a7b7a-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="a7b7a-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a7b7a-112">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a7b7a-113">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="a7b7a-113">arg : 'T</span></span>

<span data-ttu-id="a7b7a-114">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="a7b7a-115">Aux: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7b7a-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a7b7a-116">Argomento utilizzato per ritardare l'applicazione dell'operazione utilizzando l'applicazione parziale.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7b7a-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7b7a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7b7a-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a7b7a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7b7a-119">T</span><span class="sxs-lookup"><span data-stu-id="a7b7a-119">'T</span></span>

<span data-ttu-id="a7b7a-120">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7b7a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7b7a-121">See Also</span></span>

- [<span data-ttu-id="a7b7a-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a7b7a-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="a7b7a-123">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="a7b7a-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
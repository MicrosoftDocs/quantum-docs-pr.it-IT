---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operazione repeata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852230"
---
# <a name="repeata-operation"></a><span data-ttu-id="dce97-102">Operazione repeata</span><span class="sxs-lookup"><span data-stu-id="dce97-102">RepeatA operation</span></span>

<span data-ttu-id="dce97-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dce97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dce97-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dce97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dce97-105">Ripete un'operazione per un determinato numero di volte.</span><span class="sxs-lookup"><span data-stu-id="dce97-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dce97-106">Input</span><span class="sxs-lookup"><span data-stu-id="dce97-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="dce97-107">op:' TInput => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="dce97-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dce97-108">Operazione da chiamare ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="dce97-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="dce97-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dce97-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dce97-110">Numero di volte da chiamare `op` .</span><span class="sxs-lookup"><span data-stu-id="dce97-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="dce97-111">input:' TInput</span><span class="sxs-lookup"><span data-stu-id="dce97-111">input : 'TInput</span></span>

<span data-ttu-id="dce97-112">Input da passare a `op` .</span><span class="sxs-lookup"><span data-stu-id="dce97-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dce97-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dce97-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dce97-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="dce97-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="dce97-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="dce97-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="dce97-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="dce97-116">Example</span></span>

<span data-ttu-id="dce97-117">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="dce97-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="dce97-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce97-118">See Also</span></span>

- [<span data-ttu-id="dce97-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="dce97-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="dce97-120">Microsoft. Quantum. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="dce97-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="dce97-121">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="dce97-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="dce97-122">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="dce97-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)
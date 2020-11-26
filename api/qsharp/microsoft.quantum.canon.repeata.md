---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operazione repeata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205559"
---
# <a name="repeata-operation"></a><span data-ttu-id="f930c-102">Operazione repeata</span><span class="sxs-lookup"><span data-stu-id="f930c-102">RepeatA operation</span></span>

<span data-ttu-id="f930c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f930c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f930c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f930c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f930c-105">Ripete un'operazione per un determinato numero di volte.</span><span class="sxs-lookup"><span data-stu-id="f930c-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f930c-106">Input</span><span class="sxs-lookup"><span data-stu-id="f930c-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="f930c-107">op:' TInput => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="f930c-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f930c-108">Operazione da chiamare ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="f930c-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f930c-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f930c-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f930c-110">Numero di volte da chiamare `op` .</span><span class="sxs-lookup"><span data-stu-id="f930c-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f930c-111">input:' TInput</span><span class="sxs-lookup"><span data-stu-id="f930c-111">input : 'TInput</span></span>

<span data-ttu-id="f930c-112">Input da passare a `op` .</span><span class="sxs-lookup"><span data-stu-id="f930c-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f930c-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f930c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f930c-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f930c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f930c-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="f930c-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="f930c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f930c-116">See Also</span></span>

- [<span data-ttu-id="f930c-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="f930c-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f930c-118">Microsoft. Quantum. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="f930c-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f930c-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="f930c-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="f930c-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f930c-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)
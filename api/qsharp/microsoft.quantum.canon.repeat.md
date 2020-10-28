---
uid: Microsoft.Quantum.Canon.Repeat
title: Ripetere l'operazione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715599"
---
# <a name="repeat-operation"></a><span data-ttu-id="5e4c9-102">Ripetere l'operazione</span><span class="sxs-lookup"><span data-stu-id="5e4c9-102">Repeat operation</span></span>

<span data-ttu-id="5e4c9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e4c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e4c9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e4c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e4c9-105">Ripete un'operazione per un determinato numero di volte.</span><span class="sxs-lookup"><span data-stu-id="5e4c9-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="5e4c9-106">Input</span><span class="sxs-lookup"><span data-stu-id="5e4c9-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="5e4c9-107">op:' TInput = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5e4c9-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5e4c9-108">Operazione da chiamare ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="5e4c9-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="5e4c9-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e4c9-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e4c9-110">Numero di volte da chiamare `op` .</span><span class="sxs-lookup"><span data-stu-id="5e4c9-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="5e4c9-111">input:' TInput</span><span class="sxs-lookup"><span data-stu-id="5e4c9-111">input : 'TInput</span></span>

<span data-ttu-id="5e4c9-112">Input da passare a `op` .</span><span class="sxs-lookup"><span data-stu-id="5e4c9-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e4c9-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e4c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e4c9-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5e4c9-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="5e4c9-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="5e4c9-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="5e4c9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e4c9-116">See Also</span></span>

- [<span data-ttu-id="5e4c9-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="5e4c9-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="5e4c9-118">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="5e4c9-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="5e4c9-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="5e4c9-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="5e4c9-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="5e4c9-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)
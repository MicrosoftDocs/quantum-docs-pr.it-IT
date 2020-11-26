---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operazione DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209996"
---
# <a name="drawmany-operation"></a><span data-ttu-id="11493-102">Operazione DrawMany</span><span class="sxs-lookup"><span data-stu-id="11493-102">DrawMany operation</span></span>

<span data-ttu-id="11493-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="11493-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="11493-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11493-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11493-105">Ripete un'operazione per un determinato numero di campioni, raccogliendo gli output in una matrice.</span><span class="sxs-lookup"><span data-stu-id="11493-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="11493-106">Input</span><span class="sxs-lookup"><span data-stu-id="11493-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="11493-107">op:' TInput =>' TOutput</span><span class="sxs-lookup"><span data-stu-id="11493-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="11493-108">Operazione da chiamare ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="11493-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="11493-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11493-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11493-110">Numero di campioni di chiamata `op` a Collect.</span><span class="sxs-lookup"><span data-stu-id="11493-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="11493-111">input:' TInput</span><span class="sxs-lookup"><span data-stu-id="11493-111">input : 'TInput</span></span>

<span data-ttu-id="11493-112">Input da passare a `op` .</span><span class="sxs-lookup"><span data-stu-id="11493-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="11493-113">Output:' TOutput []</span><span class="sxs-lookup"><span data-stu-id="11493-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="11493-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="11493-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="11493-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="11493-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="11493-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="11493-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="11493-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11493-117">See Also</span></span>

- [<span data-ttu-id="11493-118">Microsoft. Quantum. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="11493-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
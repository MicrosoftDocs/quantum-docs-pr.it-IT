---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operazione AllowAtMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853530"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="490ed-102">Operazione AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="490ed-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="490ed-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="490ed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="490ed-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="490ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="490ed-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che una determinata operazione viene chiamata al massimo un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="490ed-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="490ed-106">Input</span><span class="sxs-lookup"><span data-stu-id="490ed-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="490ed-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="490ed-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="490ed-108">Il numero massimo di volte che è `op` possibile chiamare.</span><span class="sxs-lookup"><span data-stu-id="490ed-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="490ed-109">op:' TInput =>' TOutput è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="490ed-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="490ed-110">Operazione le cui chiamate devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="490ed-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="490ed-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="490ed-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="490ed-112">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="490ed-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="490ed-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="490ed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="490ed-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="490ed-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="490ed-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="490ed-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="490ed-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="490ed-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="490ed-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="490ed-117">Example</span></span>

<span data-ttu-id="490ed-118">Il frammento di codice seguente avrà esito negativo quando viene eseguito nei computer che supportano questa diagnostica:</span><span class="sxs-lookup"><span data-stu-id="490ed-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="490ed-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="490ed-119">Remarks</span></span>

<span data-ttu-id="490ed-120">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="490ed-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>
---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operazione AllowAtMostNCallsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202567"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="4250d-102">Operazione AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="4250d-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="4250d-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4250d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4250d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4250d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4250d-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che una determinata operazione viene chiamata al massimo un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="4250d-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4250d-106">Input</span><span class="sxs-lookup"><span data-stu-id="4250d-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="4250d-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4250d-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4250d-108">Il numero massimo di volte che è `op` possibile chiamare.</span><span class="sxs-lookup"><span data-stu-id="4250d-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="4250d-109">op:' TInput =>' TOutput è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4250d-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="4250d-110">Operazione le cui chiamate devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="4250d-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="4250d-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4250d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4250d-112">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="4250d-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4250d-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4250d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4250d-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4250d-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="4250d-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="4250d-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="4250d-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="4250d-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="4250d-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="4250d-117">Remarks</span></span>

<span data-ttu-id="4250d-118">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="4250d-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>
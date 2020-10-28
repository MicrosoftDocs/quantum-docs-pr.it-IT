---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operazione AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713065"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="a022c-102">Operazione AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="a022c-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="a022c-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a022c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a022c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a022c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a022c-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che una determinata operazione viene chiamata al massimo un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="a022c-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a022c-106">Input</span><span class="sxs-lookup"><span data-stu-id="a022c-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="a022c-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a022c-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a022c-108">Il numero massimo di volte che è `op` possibile chiamare.</span><span class="sxs-lookup"><span data-stu-id="a022c-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="a022c-109">op:' TInput =>' TOutput ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a022c-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="a022c-110">Operazione le cui chiamate devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="a022c-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="a022c-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a022c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a022c-112">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="a022c-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a022c-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a022c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a022c-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a022c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a022c-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="a022c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="a022c-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="a022c-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="a022c-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="a022c-117">Remarks</span></span>

<span data-ttu-id="a022c-118">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="a022c-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>
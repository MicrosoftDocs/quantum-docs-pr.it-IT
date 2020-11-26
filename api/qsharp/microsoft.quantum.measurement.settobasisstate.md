---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operazione SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194152"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="490ba-102">Operazione SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="490ba-102">SetToBasisState operation</span></span>

<span data-ttu-id="490ba-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="490ba-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="490ba-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="490ba-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="490ba-105">Imposta un qubit su uno stato di base di calcolo specificato misurando il qubit e applicando un flip di bit se necessario.</span><span class="sxs-lookup"><span data-stu-id="490ba-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="490ba-106">Input</span><span class="sxs-lookup"><span data-stu-id="490ba-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="490ba-107">desiderato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="490ba-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="490ba-108">Stato di base su cui deve essere impostato qubit.</span><span class="sxs-lookup"><span data-stu-id="490ba-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="490ba-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="490ba-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="490ba-110">Qubit di cui è necessario impostare lo stato.</span><span class="sxs-lookup"><span data-stu-id="490ba-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="490ba-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="490ba-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="490ba-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="490ba-112">Remarks</span></span>

<span data-ttu-id="490ba-113">Come invariante di questa operazione, la chiamata `M(q)` immediata dopo `SetToBasisState(result, q)` restituirà `result` .</span><span class="sxs-lookup"><span data-stu-id="490ba-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>
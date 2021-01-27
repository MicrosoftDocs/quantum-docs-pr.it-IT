---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operazione SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854616"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="07c12-102">Operazione SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="07c12-102">SetToBasisState operation</span></span>

<span data-ttu-id="07c12-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="07c12-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="07c12-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="07c12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="07c12-105">Imposta un qubit su uno stato di base di calcolo specificato misurando il qubit e applicando un flip di bit se necessario.</span><span class="sxs-lookup"><span data-stu-id="07c12-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="07c12-106">Input</span><span class="sxs-lookup"><span data-stu-id="07c12-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="07c12-107">desiderato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="07c12-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="07c12-108">Stato di base su cui deve essere impostato qubit.</span><span class="sxs-lookup"><span data-stu-id="07c12-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="07c12-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07c12-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07c12-110">Qubit di cui è necessario impostare lo stato.</span><span class="sxs-lookup"><span data-stu-id="07c12-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07c12-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07c12-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07c12-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="07c12-112">Remarks</span></span>

<span data-ttu-id="07c12-113">Come invariante di questa operazione, la chiamata `M(q)` immediata dopo `SetToBasisState(result, q)` restituirà `result` .</span><span class="sxs-lookup"><span data-stu-id="07c12-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>
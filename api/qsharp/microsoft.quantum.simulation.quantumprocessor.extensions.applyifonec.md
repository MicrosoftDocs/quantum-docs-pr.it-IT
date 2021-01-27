---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: Operazione ApplyIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: ae6e0d16424e745303b377e70927cda847d2f1e8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858732"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="76a32-102">Operazione ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="76a32-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="76a32-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="76a32-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="76a32-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="76a32-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="76a32-105">Input</span><span class="sxs-lookup"><span data-stu-id="76a32-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="76a32-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="76a32-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="76a32-107">onResultOneOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="76a32-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="76a32-108">oneArg: t</span><span class="sxs-lookup"><span data-stu-id="76a32-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="76a32-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76a32-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76a32-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="76a32-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76a32-111">T</span><span class="sxs-lookup"><span data-stu-id="76a32-111">'T</span></span>


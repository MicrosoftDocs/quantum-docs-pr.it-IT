---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: Operazione ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: e997cf4b20fdd2c52285191b732297ca99886c22
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230940"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="c2b6b-102">Operazione ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="c2b6b-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="c2b6b-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c2b6b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c2b6b-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c2b6b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c2b6b-105">Input</span><span class="sxs-lookup"><span data-stu-id="c2b6b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c2b6b-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="c2b6b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="c2b6b-107">onResultOneOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c2b6b-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="c2b6b-108">oneArg: t</span><span class="sxs-lookup"><span data-stu-id="c2b6b-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="c2b6b-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2b6b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2b6b-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c2b6b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2b6b-111">T</span><span class="sxs-lookup"><span data-stu-id="c2b6b-111">'T</span></span>


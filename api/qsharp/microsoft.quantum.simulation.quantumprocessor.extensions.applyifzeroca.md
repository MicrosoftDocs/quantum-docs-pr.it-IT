---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725672"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="3ddb4-102">Operazione ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="3ddb4-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="3ddb4-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3ddb4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="3ddb4-105">Input</span><span class="sxs-lookup"><span data-stu-id="3ddb4-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3ddb4-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="3ddb4-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl--adj"></a><span data-ttu-id="3ddb4-107">onResultZeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="3ddb4-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="3ddb4-108">zeroArg: t</span><span class="sxs-lookup"><span data-stu-id="3ddb4-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="3ddb4-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ddb4-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3ddb4-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3ddb4-111">T</span><span class="sxs-lookup"><span data-stu-id="3ddb4-111">'T</span></span>


---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709467"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="9fb08-102">Operazione ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="9fb08-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="9fb08-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="9fb08-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="9fb08-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fb08-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="9fb08-105">Input</span><span class="sxs-lookup"><span data-stu-id="9fb08-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="9fb08-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="9fb08-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="9fb08-107">onResultZeroOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fb08-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="9fb08-108">zeroArg: t</span><span class="sxs-lookup"><span data-stu-id="9fb08-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-ctl"></a><span data-ttu-id="9fb08-109">onResultOneOp:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fb08-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="9fb08-110">oneArg:' U</span><span class="sxs-lookup"><span data-stu-id="9fb08-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="9fb08-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fb08-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9fb08-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9fb08-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fb08-113">T</span><span class="sxs-lookup"><span data-stu-id="9fb08-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="9fb08-114">' U</span><span class="sxs-lookup"><span data-stu-id="9fb08-114">'U</span></span>

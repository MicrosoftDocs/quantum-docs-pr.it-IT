---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Operazione ApplyConditionallyCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: e456ed5d8f7f17a914401473948c89c020174903
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720174"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="87030-102">Operazione ApplyConditionallyCA</span><span class="sxs-lookup"><span data-stu-id="87030-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="87030-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="87030-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="87030-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87030-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="87030-105">Input</span><span class="sxs-lookup"><span data-stu-id="87030-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="87030-106">measurementResults: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="87030-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="87030-107">resultsValues: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="87030-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl--adj"></a><span data-ttu-id="87030-108">onEqualOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="87030-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="87030-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="87030-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl--adj"></a><span data-ttu-id="87030-110">onNonEqualOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="87030-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="87030-111">nonEqualArg:' U</span><span class="sxs-lookup"><span data-stu-id="87030-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="87030-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87030-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87030-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="87030-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87030-114">T</span><span class="sxs-lookup"><span data-stu-id="87030-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="87030-115">' U</span><span class="sxs-lookup"><span data-stu-id="87030-115">'U</span></span>


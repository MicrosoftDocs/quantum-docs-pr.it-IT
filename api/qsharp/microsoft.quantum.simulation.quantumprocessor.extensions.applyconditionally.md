---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Operazione ApplyConditionally
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710534"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="b6764-102">Operazione ApplyConditionally</span><span class="sxs-lookup"><span data-stu-id="b6764-102">ApplyConditionally operation</span></span>

<span data-ttu-id="b6764-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b6764-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b6764-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6764-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="b6764-105">Input</span><span class="sxs-lookup"><span data-stu-id="b6764-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="b6764-106">measurementResults: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="b6764-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="b6764-107">resultsValues: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="b6764-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="b6764-108">onEqualOp:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b6764-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="b6764-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="b6764-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="b6764-110">onNonEqualOp:' U = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b6764-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="b6764-111">nonEqualArg:' U</span><span class="sxs-lookup"><span data-stu-id="b6764-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b6764-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6764-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b6764-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b6764-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6764-114">T</span><span class="sxs-lookup"><span data-stu-id="b6764-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b6764-115">' U</span><span class="sxs-lookup"><span data-stu-id="b6764-115">'U</span></span>


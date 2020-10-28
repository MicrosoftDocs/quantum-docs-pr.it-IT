---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Operazione ApplyIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 6de4fcf86495136f2caec6fb6f873a18d751c977
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725686"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="72105-102">Operazione ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="72105-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="72105-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="72105-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="72105-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72105-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="72105-105">Input</span><span class="sxs-lookup"><span data-stu-id="72105-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="72105-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="72105-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="72105-107">onResultZeroOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72105-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="72105-108">zeroArg: t</span><span class="sxs-lookup"><span data-stu-id="72105-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="72105-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72105-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72105-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="72105-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72105-111">T</span><span class="sxs-lookup"><span data-stu-id="72105-111">'T</span></span>


---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: f7dd30171acd3786c6d012b82b9abf99f9042caf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858259"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="a41c8-102">Operazione ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="a41c8-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="a41c8-103">Spazio dei nomi: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a41c8-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a41c8-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a41c8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a41c8-105">Input</span><span class="sxs-lookup"><span data-stu-id="a41c8-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a41c8-106">measurementResult: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="a41c8-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="a41c8-107">onResultZeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a41c8-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="a41c8-108">zeroArg: t</span><span class="sxs-lookup"><span data-stu-id="a41c8-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a41c8-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a41c8-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a41c8-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a41c8-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a41c8-111">T</span><span class="sxs-lookup"><span data-stu-id="a41c8-111">'T</span></span>


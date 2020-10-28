---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operazione SampleTransformedContinuousDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723975"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="f3f5f-102">Operazione SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="f3f5f-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="f3f5f-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f3f5f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f3f5f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3f5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3f5f-105">Operazione solo interna per il campionamento da distribuzioni trasformate.</span><span class="sxs-lookup"><span data-stu-id="f3f5f-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="f3f5f-106">Deve essere usato solo tramite un'applicazione parziale.</span><span class="sxs-lookup"><span data-stu-id="f3f5f-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="f3f5f-107">Input</span><span class="sxs-lookup"><span data-stu-id="f3f5f-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="f3f5f-108">trasformazione: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3f5f-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="f3f5f-109">distribuzione: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f3f5f-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="f3f5f-110">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3f5f-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>


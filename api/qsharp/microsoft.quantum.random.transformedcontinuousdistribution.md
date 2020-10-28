---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710940"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="eec19-102">TransformedContinuousDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="eec19-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="eec19-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="eec19-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="eec19-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eec19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eec19-105">Data una distribuzione continua, restituisce una nuova distribuzione che trasforma l'originale in base a una determinata funzione.</span><span class="sxs-lookup"><span data-stu-id="eec19-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="eec19-106">Input</span><span class="sxs-lookup"><span data-stu-id="eec19-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="eec19-107">trasformazione: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eec19-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eec19-108">Funzione che trasforma le variabili della distribuzione originale nella distribuzione trasformata.</span><span class="sxs-lookup"><span data-stu-id="eec19-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="eec19-109">distribuzione: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="eec19-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="eec19-110">Distribuzione originale da trasformare.</span><span class="sxs-lookup"><span data-stu-id="eec19-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="eec19-111">Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="eec19-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="eec19-112">Nuova distribuzione correlata a `distribution` dalla trasformazione fornita da `transform` .</span><span class="sxs-lookup"><span data-stu-id="eec19-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>
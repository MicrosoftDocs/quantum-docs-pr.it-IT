---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226265"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="cc809-102">TransformedContinuousDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="cc809-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="cc809-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cc809-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cc809-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cc809-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cc809-105">Data una distribuzione continua, restituisce una nuova distribuzione che trasforma l'originale in base a una determinata funzione.</span><span class="sxs-lookup"><span data-stu-id="cc809-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="cc809-106">Input</span><span class="sxs-lookup"><span data-stu-id="cc809-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="cc809-107">trasformazione: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc809-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc809-108">Funzione che trasforma le variabili della distribuzione originale nella distribuzione trasformata.</span><span class="sxs-lookup"><span data-stu-id="cc809-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="cc809-109">distribuzione: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="cc809-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="cc809-110">Distribuzione originale da trasformare.</span><span class="sxs-lookup"><span data-stu-id="cc809-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="cc809-111">Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="cc809-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="cc809-112">Nuova distribuzione correlata a `distribution` dalla trasformazione fornita da `transform` .</span><span class="sxs-lookup"><span data-stu-id="cc809-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>
---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196362"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="b6f5e-102">InferredLabels (funzione)</span><span class="sxs-lookup"><span data-stu-id="b6f5e-102">InferredLabels function</span></span>

<span data-ttu-id="b6f5e-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b6f5e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b6f5e-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b6f5e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b6f5e-105">Data una matrice di probabilità di classificazione e una distorsione, restituisce l'etichetta dedotta da ogni probabilità.</span><span class="sxs-lookup"><span data-stu-id="b6f5e-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b6f5e-106">Input</span><span class="sxs-lookup"><span data-stu-id="b6f5e-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="b6f5e-107">distorsione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6f5e-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6f5e-108">Distorsione tra due classi, in genere il risultato del training di un classificatore.</span><span class="sxs-lookup"><span data-stu-id="b6f5e-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="b6f5e-109">probabilità: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b6f5e-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b6f5e-110">Matrice di probabilità di classificazione per un set di esempi, in genere risultante dalla stima delle frequenze di classificazione.</span><span class="sxs-lookup"><span data-stu-id="b6f5e-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="b6f5e-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6f5e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6f5e-112">Etichetta dedotta da ogni probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="b6f5e-112">The label inferred from each classification probability.</span></span>
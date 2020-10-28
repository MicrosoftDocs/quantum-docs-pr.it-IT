---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722480"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="276a7-102">InferredLabels (funzione)</span><span class="sxs-lookup"><span data-stu-id="276a7-102">InferredLabels function</span></span>

<span data-ttu-id="276a7-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="276a7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="276a7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="276a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="276a7-105">Data una matrice di probabilità di classificazione e una distorsione, restituisce l'etichetta dedotta da ogni probabilità.</span><span class="sxs-lookup"><span data-stu-id="276a7-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="276a7-106">Input</span><span class="sxs-lookup"><span data-stu-id="276a7-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="276a7-107">distorsione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="276a7-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="276a7-108">Distorsione tra due classi, in genere il risultato del training di un classificatore.</span><span class="sxs-lookup"><span data-stu-id="276a7-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="276a7-109">probabilità: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="276a7-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="276a7-110">Matrice di probabilità di classificazione per un set di esempi, in genere risultante dalla stima delle frequenze di classificazione.</span><span class="sxs-lookup"><span data-stu-id="276a7-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="276a7-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="276a7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="276a7-112">Etichetta dedotta da ogni probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="276a7-112">The label inferred from each classification probability.</span></span>
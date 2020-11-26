---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operazione EstimateClassificationProbabilities
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211900"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="5bbd8-102">Operazione EstimateClassificationProbabilities</span><span class="sxs-lookup"><span data-stu-id="5bbd8-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="5bbd8-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5bbd8-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5bbd8-105">Dato un set di esempi e un classificatore sequenziale, in viene stimata la probabilità di classificazione per tali campioni, misurando ripetutamente l'output del classificatore su ciascun campione.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="5bbd8-106">Input</span><span class="sxs-lookup"><span data-stu-id="5bbd8-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="5bbd8-107">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5bbd8-108">Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="5bbd8-109">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="5bbd8-110">Modello sequenziale da utilizzare per stimare le probabilità di classificazione per gli esempi specificati.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="5bbd8-111">Esempi: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="5bbd8-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="5bbd8-112">Matrice di vettori di funzionalità per ogni campione da classificare.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="5bbd8-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5bbd8-114">Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="5bbd8-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5bbd8-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5bbd8-116">Matrice di stime della probabilità di classificazione per ogni esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-116">An array of estimates of the classification probability for each given sample.</span></span>
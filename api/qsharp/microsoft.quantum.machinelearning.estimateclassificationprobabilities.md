---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operazione EstimateClassificationProbabilities
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709789"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="8c4f3-102">Operazione EstimateClassificationProbabilities</span><span class="sxs-lookup"><span data-stu-id="8c4f3-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="8c4f3-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8c4f3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8c4f3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c4f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c4f3-105">Dato un set di esempi e un classificatore sequenziale, in viene stimata la probabilità di classificazione per tali campioni, misurando ripetutamente l'output del classificatore su ciascun campione.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="8c4f3-106">Input</span><span class="sxs-lookup"><span data-stu-id="8c4f3-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="8c4f3-107">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8c4f3-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8c4f3-108">Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="8c4f3-109">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="8c4f3-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="8c4f3-110">Modello sequenziale da utilizzare per stimare le probabilità di classificazione per gli esempi specificati.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="8c4f3-111">Esempi: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="8c4f3-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="8c4f3-112">Matrice di vettori di funzionalità per ogni campione da classificare.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="8c4f3-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c4f3-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c4f3-114">Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="8c4f3-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8c4f3-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8c4f3-116">Matrice di stime della probabilità di classificazione per ogni esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="8c4f3-116">An array of estimates of the classification probability for each given sample.</span></span>
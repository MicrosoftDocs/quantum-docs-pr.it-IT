---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operazione EstimateClassificationProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853951"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="60c5e-102">Operazione EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="60c5e-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="60c5e-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="60c5e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="60c5e-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="60c5e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="60c5e-105">Dato un esempio e un classificatore sequenziale, stima la probabilità di classificazione per l'esempio misurando ripetutamente l'output del classificatore sull'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="60c5e-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="60c5e-106">Input</span><span class="sxs-lookup"><span data-stu-id="60c5e-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="60c5e-107">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60c5e-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="60c5e-108">Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="60c5e-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="60c5e-109">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="60c5e-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="60c5e-110">Modello sequenziale da utilizzare per stimare la probabilità di classificazione per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="60c5e-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="60c5e-111">esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="60c5e-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="60c5e-112">Vettore di funzionalità per l'esempio da classificare.</span><span class="sxs-lookup"><span data-stu-id="60c5e-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="60c5e-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60c5e-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60c5e-114">Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="60c5e-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="60c5e-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60c5e-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="60c5e-116">Stima della probabilità di classificazione per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="60c5e-116">An estimate of the classification probability for the given sample.</span></span>
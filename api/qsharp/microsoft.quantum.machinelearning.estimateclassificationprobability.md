---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operazione EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709775"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="d4d40-102">Operazione EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="d4d40-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="d4d40-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d4d40-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d4d40-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4d40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4d40-105">Dato un esempio e un classificatore sequenziale, stima la probabilità di classificazione per l'esempio misurando ripetutamente l'output del classificatore sull'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="d4d40-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d4d40-106">Input</span><span class="sxs-lookup"><span data-stu-id="d4d40-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="d4d40-107">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d4d40-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d4d40-108">Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="d4d40-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="d4d40-109">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="d4d40-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="d4d40-110">Modello sequenziale da utilizzare per stimare la probabilità di classificazione per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="d4d40-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="d4d40-111">esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d4d40-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d4d40-112">Vettore di funzionalità per l'esempio da classificare.</span><span class="sxs-lookup"><span data-stu-id="d4d40-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d4d40-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4d40-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4d40-114">Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="d4d40-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="d4d40-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d4d40-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d4d40-116">Stima della probabilità di classificazione per l'esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="d4d40-116">An estimate of the classification probability for the given sample.</span></span>
---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operazione _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856193"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="97bf7-102">Operazione _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="97bf7-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="97bf7-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="97bf7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="97bf7-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="97bf7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="97bf7-105">Eseguire un periodo di training del classificatore sequenziale su un subset di campioni di dati.</span><span class="sxs-lookup"><span data-stu-id="97bf7-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="97bf7-106">Input</span><span class="sxs-lookup"><span data-stu-id="97bf7-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="97bf7-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="97bf7-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="97bf7-108">pianificazione: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="97bf7-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="97bf7-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97bf7-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97bf7-110">Numero di passaggi sfumatura da intraprendere tra i punti di punteggio.</span><span class="sxs-lookup"><span data-stu-id="97bf7-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="97bf7-111">Per un'accuratezza ottimale, impostare su 1.</span><span class="sxs-lookup"><span data-stu-id="97bf7-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="97bf7-112">opzioni: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="97bf7-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="97bf7-113">Opzioni da utilizzare nel training.</span><span class="sxs-lookup"><span data-stu-id="97bf7-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="97bf7-114">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="97bf7-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="97bf7-115">Modello sequenziale di cui eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="97bf7-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="97bf7-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97bf7-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97bf7-117">Il numero migliore di classificazioni errate osservate in epoche precedenti.</span><span class="sxs-lookup"><span data-stu-id="97bf7-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="97bf7-118">Output: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="97bf7-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="97bf7-119">Il minor numero di classificazioni errate osservate fino a questo periodo.</span><span class="sxs-lookup"><span data-stu-id="97bf7-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="97bf7-120">È stato trovato il nuovo modello sequenziale migliore.</span><span class="sxs-lookup"><span data-stu-id="97bf7-120">The new best sequential model found.</span></span>
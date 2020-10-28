---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operazione TrainSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711304"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="872ff-102">Operazione TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="872ff-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="872ff-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="872ff-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="872ff-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="872ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="872ff-105">Data la struttura di un classificatore sequenziale, addestra il classificatore su un determinato set di training con etichetta.</span><span class="sxs-lookup"><span data-stu-id="872ff-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="872ff-106">Input</span><span class="sxs-lookup"><span data-stu-id="872ff-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="872ff-107">modelli: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="872ff-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="872ff-108">Matrice di modelli da utilizzare come punti di partenza durante il training.</span><span class="sxs-lookup"><span data-stu-id="872ff-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="872ff-109">Esempi: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="872ff-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="872ff-110">Set di dati di training con etichette che verranno utilizzati per eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="872ff-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="872ff-111">opzioni: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="872ff-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="872ff-112">Configurazione da usare durante il training; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" per ulteriori informazioni, vedere e.</span><span class="sxs-lookup"><span data-stu-id="872ff-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="872ff-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="872ff-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="872ff-114">Pianificazione di campionamento da usare quando si selezionano esempi dai dati di training durante i passaggi di training.</span><span class="sxs-lookup"><span data-stu-id="872ff-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="872ff-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="872ff-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="872ff-116">Pianificazione di campionamento da usare quando si selezionano esempi dai dati di training quando si seleziona il punto iniziale che ha determinato il Punteggio di classificazione migliore.</span><span class="sxs-lookup"><span data-stu-id="872ff-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="872ff-117">Output: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="872ff-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="872ff-118">Parametrizzazione del classificatore specificato e distorsione tra le due classi, insieme corrispondenti al risultato migliore da ognuno dei punti di inizio specificati.</span><span class="sxs-lookup"><span data-stu-id="872ff-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="872ff-119">Numero di mancati riscontri osservati nel modello di classificazione migliore.</span><span class="sxs-lookup"><span data-stu-id="872ff-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="872ff-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="872ff-120">See Also</span></span>

- [<span data-ttu-id="872ff-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="872ff-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="872ff-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="872ff-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Tipo definito dall'utente TrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842773"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="4c878-102">Tipo definito dall'utente TrainingOptions</span><span class="sxs-lookup"><span data-stu-id="4c878-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="4c878-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4c878-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4c878-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4c878-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4c878-105">Raccolta di opzioni da utilizzare per i classificatori Quantum di training.</span><span class="sxs-lookup"><span data-stu-id="4c878-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="4c878-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="4c878-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="4c878-107">LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c878-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c878-108">Velocità di apprendimento in base alla quale è necessario ridimensionare le sfumature quando si aggiornano i parametri del modello durante i passaggi di training.</span><span class="sxs-lookup"><span data-stu-id="4c878-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="4c878-109">Tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c878-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c878-110">La tolleranza di approssimazione da usare quando si preparano campioni come stati Quantum.</span><span class="sxs-lookup"><span data-stu-id="4c878-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="4c878-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c878-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c878-112">Numero di campioni da usare in ogni minibatch di training.</span><span class="sxs-lookup"><span data-stu-id="4c878-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="4c878-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c878-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c878-114">Il numero di volte in cui misurare ogni risultato della classificazione per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="4c878-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="4c878-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c878-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c878-116">Numero massimo di epoche per il training di ogni modello.</span><span class="sxs-lookup"><span data-stu-id="4c878-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="4c878-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c878-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c878-118">Il numero massimo di volte in cui è consentita l'esecuzione di un periodo di training, ovvero una sfumatura di circa zero, prima dell'errore</span><span class="sxs-lookup"><span data-stu-id="4c878-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="4c878-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c878-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c878-120">Quantità di ridimensionare i modelli bloccati da prima di ritentare un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4c878-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="4c878-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c878-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c878-122">Numero di passaggi sfumatura da intraprendere tra i punti di punteggio.</span><span class="sxs-lookup"><span data-stu-id="4c878-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="4c878-123">Per un'accuratezza ottimale, impostare su 1.</span><span class="sxs-lookup"><span data-stu-id="4c878-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="4c878-124">VerboseMessage: [](xref:microsoft.quantum.lang-ref.string) -> [unità](xref:microsoft.quantum.lang-ref.unit) di stringa</span><span class="sxs-lookup"><span data-stu-id="4c878-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="4c878-125">Funzione che può essere utilizzata per fornire commenti e suggerimenti dettagliati.</span><span class="sxs-lookup"><span data-stu-id="4c878-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c878-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c878-126">Remarks</span></span>

<span data-ttu-id="4c878-127">Questo tipo definito dall'utente non deve essere creato direttamente, bensì deve essere specificato chiamando @"microsoft.quantum.machinelearning.defaulttrainingoptions" e quindi usando l' `w/` operatore per eseguire l'override di impostazioni predefinite diverse.</span><span class="sxs-lookup"><span data-stu-id="4c878-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="4c878-128">Ad esempio, per usare misure 100.000 e al massimo 8 epoche di training:</span><span class="sxs-lookup"><span data-stu-id="4c878-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="4c878-129">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4c878-129">References</span></span>

- [<span data-ttu-id="4c878-130">arXiv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="4c878-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)
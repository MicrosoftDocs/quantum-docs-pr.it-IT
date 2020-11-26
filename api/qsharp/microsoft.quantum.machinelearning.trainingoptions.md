---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Tipo definito dall'utente TrainingOptions
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196124"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="dec8c-102">Tipo definito dall'utente TrainingOptions</span><span class="sxs-lookup"><span data-stu-id="dec8c-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="dec8c-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dec8c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dec8c-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dec8c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="dec8c-105">Raccolta di opzioni da utilizzare per i classificatori Quantum di training.</span><span class="sxs-lookup"><span data-stu-id="dec8c-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="dec8c-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="dec8c-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="dec8c-107">LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dec8c-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dec8c-108">Velocità di apprendimento in base alla quale è necessario ridimensionare le sfumature quando si aggiornano i parametri del modello durante i passaggi di training.</span><span class="sxs-lookup"><span data-stu-id="dec8c-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="dec8c-109">Tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dec8c-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dec8c-110">La tolleranza di approssimazione da usare quando si preparano campioni come stati Quantum.</span><span class="sxs-lookup"><span data-stu-id="dec8c-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="dec8c-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dec8c-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dec8c-112">Numero di campioni da usare in ogni minibatch di training.</span><span class="sxs-lookup"><span data-stu-id="dec8c-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="dec8c-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dec8c-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dec8c-114">Il numero di volte in cui misurare ogni risultato della classificazione per stimare la probabilità di classificazione.</span><span class="sxs-lookup"><span data-stu-id="dec8c-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="dec8c-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dec8c-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dec8c-116">Numero massimo di epoche per il training di ogni modello.</span><span class="sxs-lookup"><span data-stu-id="dec8c-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="dec8c-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dec8c-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dec8c-118">Il numero massimo di volte in cui è consentita l'esecuzione di un periodo di training, ovvero una sfumatura di circa zero, prima dell'errore</span><span class="sxs-lookup"><span data-stu-id="dec8c-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="dec8c-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dec8c-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dec8c-120">Quantità di ridimensionare i modelli bloccati da prima di ritentare un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="dec8c-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="dec8c-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dec8c-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dec8c-122">Numero di passaggi sfumatura da intraprendere tra i punti di punteggio.</span><span class="sxs-lookup"><span data-stu-id="dec8c-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="dec8c-123">Per un'accuratezza ottimale, impostare su 1.</span><span class="sxs-lookup"><span data-stu-id="dec8c-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="dec8c-124">VerboseMessage: [String](xref:microsoft.quantum.lang-ref.string) -> [unità](xref:microsoft.quantum.lang-ref.unit) di stringa</span><span class="sxs-lookup"><span data-stu-id="dec8c-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="dec8c-125">Funzione che può essere utilizzata per fornire commenti e suggerimenti dettagliati.</span><span class="sxs-lookup"><span data-stu-id="dec8c-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="dec8c-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dec8c-126">Remarks</span></span>

<span data-ttu-id="dec8c-127">Questo tipo definito dall'utente non deve essere creato direttamente, bensì deve essere specificato chiamando @"microsoft.quantum.machinelearning.defaulttrainingoptions" e quindi usando l' `w/` operatore per eseguire l'override di impostazioni predefinite diverse.</span><span class="sxs-lookup"><span data-stu-id="dec8c-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="dec8c-128">Ad esempio, per usare misure 100.000 e al massimo 8 epoche di training:</span><span class="sxs-lookup"><span data-stu-id="dec8c-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="dec8c-129">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="dec8c-129">References</span></span>

- [<span data-ttu-id="dec8c-130">arXiv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="dec8c-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)
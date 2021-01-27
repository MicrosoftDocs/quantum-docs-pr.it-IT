---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Operazione ValidateSequentialClassifier
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: c100c5786b18996ce13067f1c4618cf0189578f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848986"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="d7f49-102">Operazione ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="d7f49-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="d7f49-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d7f49-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d7f49-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d7f49-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d7f49-105">Convalida un classificatore sequenziale specificato rispetto a un determinato set di campioni con etichette precedenti.</span><span class="sxs-lookup"><span data-stu-id="d7f49-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="d7f49-106">Input</span><span class="sxs-lookup"><span data-stu-id="d7f49-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="d7f49-107">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="d7f49-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="d7f49-108">Modello sequenziale da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d7f49-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="d7f49-109">Esempi: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="d7f49-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="d7f49-110">Esempi da utilizzare per convalidare il modello specificato.</span><span class="sxs-lookup"><span data-stu-id="d7f49-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="d7f49-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d7f49-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d7f49-112">Tolleranza di approssimazione da utilizzare per la codifica di ogni campione come input per il classificatore sequenziale.</span><span class="sxs-lookup"><span data-stu-id="d7f49-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d7f49-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7f49-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7f49-114">Numero di misurazioni da utilizzare per la classificazione di ogni campione.</span><span class="sxs-lookup"><span data-stu-id="d7f49-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="d7f49-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d7f49-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d7f49-116">Pianificazione mediante la quale è necessario disegnare gli esempi dal set di convalida.</span><span class="sxs-lookup"><span data-stu-id="d7f49-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="d7f49-117">Output: [validationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="d7f49-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="d7f49-118">Risultati della convalida specificata.</span><span class="sxs-lookup"><span data-stu-id="d7f49-118">The results of the given validation.</span></span>
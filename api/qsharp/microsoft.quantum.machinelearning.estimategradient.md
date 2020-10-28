---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operazione EstimateGradient
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719970"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="43efb-102">Operazione EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="43efb-102">EstimateGradient operation</span></span>

<span data-ttu-id="43efb-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="43efb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="43efb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43efb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43efb-105">Stima la sfumatura di training per un classificatore sequenziale in un modello specifico e per un input codificato specificato.</span><span class="sxs-lookup"><span data-stu-id="43efb-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="43efb-106">Input</span><span class="sxs-lookup"><span data-stu-id="43efb-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="43efb-107">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="43efb-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="43efb-108">Modello sequenziale di cui è necessario stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="43efb-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="43efb-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="43efb-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="43efb-110">Input per il classificatore sequenziale, codificato in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="43efb-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="43efb-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43efb-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43efb-112">Numero di misurazioni da utilizzare per stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="43efb-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="43efb-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="43efb-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="43efb-114">Stima della sfumatura di training ai parametri di input e di modello specificati.</span><span class="sxs-lookup"><span data-stu-id="43efb-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="43efb-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="43efb-115">Remarks</span></span>

<span data-ttu-id="43efb-116">Questa operazione usa un test Hadamard e la tecnica Shift del parametro insieme per stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="43efb-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>
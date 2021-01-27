---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operazione EstimateGradient
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844392"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="22835-102">Operazione EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="22835-102">EstimateGradient operation</span></span>

<span data-ttu-id="22835-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="22835-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="22835-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="22835-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="22835-105">Stima la sfumatura di training per un classificatore sequenziale in un modello specifico e per un input codificato specificato.</span><span class="sxs-lookup"><span data-stu-id="22835-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="22835-106">Input</span><span class="sxs-lookup"><span data-stu-id="22835-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="22835-107">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="22835-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="22835-108">Modello sequenziale di cui è necessario stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="22835-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="22835-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="22835-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="22835-110">Input per il classificatore sequenziale, codificato in un'operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="22835-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="22835-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22835-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22835-112">Numero di misurazioni da utilizzare per stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="22835-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="22835-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22835-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="22835-114">Stima della sfumatura di training ai parametri di input e di modello specificati.</span><span class="sxs-lookup"><span data-stu-id="22835-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="22835-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="22835-115">Remarks</span></span>

<span data-ttu-id="22835-116">Questa operazione usa un test Hadamard e la tecnica Shift del parametro insieme per stimare la sfumatura.</span><span class="sxs-lookup"><span data-stu-id="22835-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>
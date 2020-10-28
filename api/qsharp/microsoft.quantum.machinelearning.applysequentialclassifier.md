---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: Operazione ApplySequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720546"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="eed70-102">Operazione ApplySequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="eed70-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="eed70-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="eed70-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="eed70-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eed70-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eed70-105">Data la struttura e la parametrizzazione di un classificatore sequenziale, applica il classificatore a un registro di qubits.</span><span class="sxs-lookup"><span data-stu-id="eed70-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eed70-106">Input</span><span class="sxs-lookup"><span data-stu-id="eed70-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="eed70-107">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="eed70-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="eed70-108">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eed70-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eed70-109">Registro di destinazione a cui deve essere applicato il classificatore.</span><span class="sxs-lookup"><span data-stu-id="eed70-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eed70-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eed70-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


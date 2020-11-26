---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211662"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="0a1ef-102">NQubitsRequired (funzione)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-102">NQubitsRequired function</span></span>

<span data-ttu-id="0a1ef-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0a1ef-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0a1ef-105">Restituisce il numero di qubits necessari per applicare un classificatore sequenziale specificato.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="0a1ef-106">Input</span><span class="sxs-lookup"><span data-stu-id="0a1ef-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="0a1ef-107">Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="0a1ef-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a1ef-109">Dimensione minima di un registro in cui è possibile applicare il classificatore sequenziale.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>
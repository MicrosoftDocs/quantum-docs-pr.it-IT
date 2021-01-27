---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848433"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="adc23-102">FeatureRegisterSize (funzione)</span><span class="sxs-lookup"><span data-stu-id="adc23-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="adc23-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="adc23-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="adc23-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="adc23-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="adc23-105">Restituisce il numero di qubits necessari per codificare un vettore di funzionalità specifico.</span><span class="sxs-lookup"><span data-stu-id="adc23-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="adc23-106">Input</span><span class="sxs-lookup"><span data-stu-id="adc23-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="adc23-107">esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="adc23-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="adc23-108">Vettore di funzionalità di esempio da codificare in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="adc23-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="adc23-109">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adc23-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adc23-110">Dimensioni necessarie per codificare `sample` in un registro qubit, espresse come numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="adc23-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>
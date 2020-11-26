---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211747"
---
# <a name="inputencoder-function"></a><span data-ttu-id="30a0a-102">InputEncoder (funzione)</span><span class="sxs-lookup"><span data-stu-id="30a0a-102">InputEncoder function</span></span>

<span data-ttu-id="30a0a-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="30a0a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="30a0a-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="30a0a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="30a0a-105">Dato un set di coefficienti e una tolleranza, restituisce un'operazione di preparazione dello stato che prepara ogni coefficiente come l'ampiezza corrispondente di uno stato di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="30a0a-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="30a0a-106">Input</span><span class="sxs-lookup"><span data-stu-id="30a0a-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="30a0a-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="30a0a-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="30a0a-108">Coefficienti da codificare in uno stato di input.</span><span class="sxs-lookup"><span data-stu-id="30a0a-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="30a0a-109">Output: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="30a0a-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="30a0a-110">Operazione di preparazione dello stato che prepara i coefficienti specificati come stato di input in un determinato registro.</span><span class="sxs-lookup"><span data-stu-id="30a0a-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>
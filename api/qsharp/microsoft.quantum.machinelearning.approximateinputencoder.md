---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856170"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="889ae-102">ApproximateInputEncoder (funzione)</span><span class="sxs-lookup"><span data-stu-id="889ae-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="889ae-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="889ae-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="889ae-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="889ae-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="889ae-105">Dato un set di coefficienti e una tolleranza, restituisce un'operazione di preparazione dello stato che prepara ogni coefficiente come l'ampiezza corrispondente di uno stato di base computazionale, fino alla tolleranza specificata.</span><span class="sxs-lookup"><span data-stu-id="889ae-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="889ae-106">Input</span><span class="sxs-lookup"><span data-stu-id="889ae-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="889ae-107">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="889ae-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="889ae-108">Tolleranza di approssimazione da utilizzare per la codifica dei coefficienti specificati in uno stato di input.</span><span class="sxs-lookup"><span data-stu-id="889ae-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="889ae-109">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="889ae-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="889ae-110">Coefficienti da codificare in uno stato di input.</span><span class="sxs-lookup"><span data-stu-id="889ae-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="889ae-111">Output: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="889ae-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="889ae-112">Operazione di preparazione dello stato che prepara i coefficienti specificati come stato di input in un determinato registro.</span><span class="sxs-lookup"><span data-stu-id="889ae-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>
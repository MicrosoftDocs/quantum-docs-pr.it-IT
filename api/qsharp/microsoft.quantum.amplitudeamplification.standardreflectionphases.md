---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843907"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="d14c2-102">StandardReflectionPhases (funzione)</span><span class="sxs-lookup"><span data-stu-id="d14c2-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="d14c2-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d14c2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d14c2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d14c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d14c2-105">Calcola le fasi di Reflection parziali per l'amplificazione dell'ampiezza standard.</span><span class="sxs-lookup"><span data-stu-id="d14c2-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="d14c2-106">Input</span><span class="sxs-lookup"><span data-stu-id="d14c2-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="d14c2-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d14c2-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d14c2-108">Numero di iterazioni di amplificazione dell'ampiezza per generare fasi di Reflection parziali per.</span><span class="sxs-lookup"><span data-stu-id="d14c2-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="d14c2-109">Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d14c2-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d14c2-110">Operazione che implementa le fasi specificate come riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="d14c2-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="d14c2-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="d14c2-111">Remarks</span></span>

<span data-ttu-id="d14c2-112">Tutte le fasi sono $ \Pi $, ad eccezione della prima Reflection sullo stato di avvio e dell'ultima Reflection sullo stato di destinazione, ovvero $0 $.</span><span class="sxs-lookup"><span data-stu-id="d14c2-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>
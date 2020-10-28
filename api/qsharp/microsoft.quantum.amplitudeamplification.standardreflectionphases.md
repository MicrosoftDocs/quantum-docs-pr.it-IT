---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721735"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="691ef-102">StandardReflectionPhases (funzione)</span><span class="sxs-lookup"><span data-stu-id="691ef-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="691ef-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="691ef-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="691ef-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="691ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="691ef-105">Calcola le fasi di Reflection parziali per l'amplificazione dell'ampiezza standard.</span><span class="sxs-lookup"><span data-stu-id="691ef-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="691ef-106">Input</span><span class="sxs-lookup"><span data-stu-id="691ef-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="691ef-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="691ef-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="691ef-108">Numero di iterazioni di amplificazione dell'ampiezza per generare fasi di Reflection parziali per.</span><span class="sxs-lookup"><span data-stu-id="691ef-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="691ef-109">Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="691ef-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="691ef-110">Operazione che implementa le fasi specificate come riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="691ef-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="691ef-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="691ef-111">Remarks</span></span>

<span data-ttu-id="691ef-112">Tutte le fasi sono $ \Pi $, ad eccezione della prima Reflection sullo stato di avvio e dell'ultima Reflection sullo stato di destinazione, ovvero $0 $.</span><span class="sxs-lookup"><span data-stu-id="691ef-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>
---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721861"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="ce779-102">FixedPointReflectionPhases (funzione)</span><span class="sxs-lookup"><span data-stu-id="ce779-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="ce779-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ce779-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ce779-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce779-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce779-105">Calcola le fasi di Reflection parziali per l'amplificazione dell'ampiezza a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="ce779-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="ce779-106">Input</span><span class="sxs-lookup"><span data-stu-id="ce779-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="ce779-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce779-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce779-108">Numero di query per la preparazione dello stato Oracle.</span><span class="sxs-lookup"><span data-stu-id="ce779-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="ce779-109">Deve essere un intero dispari.</span><span class="sxs-lookup"><span data-stu-id="ce779-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="ce779-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ce779-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ce779-111">Probabilità di riuscita minima di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce779-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="ce779-112">Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ce779-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ce779-113">Matrice di fasi che è possibile usare nell'implementazione dell'algoritmo Quantum a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="ce779-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="ce779-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ce779-114">References</span></span>

<span data-ttu-id="ce779-115">Si usano le fasi nell'"amplificazione dell'ampiezza a virgola fissa con un numero ottimale di query"</span><span class="sxs-lookup"><span data-stu-id="ce779-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="ce779-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Vedere anche "metodologia di controlli Quantum compositi"</span><span class="sxs-lookup"><span data-stu-id="ce779-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="ce779-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) per le fasi nel `RotationPhases` formato.</span><span class="sxs-lookup"><span data-stu-id="ce779-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>
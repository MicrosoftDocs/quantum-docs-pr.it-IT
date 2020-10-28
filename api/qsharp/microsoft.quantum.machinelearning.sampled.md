---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Sampled (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722424"
---
# <a name="sampled-function"></a><span data-ttu-id="43d0d-102">Sampled (funzione)</span><span class="sxs-lookup"><span data-stu-id="43d0d-102">Sampled function</span></span>

<span data-ttu-id="43d0d-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="43d0d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="43d0d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43d0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43d0d-105">Esegue il campionamento di una matrice specificata, usando la pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="43d0d-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="43d0d-106">Input</span><span class="sxs-lookup"><span data-stu-id="43d0d-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="43d0d-107">pianificazione: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="43d0d-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="43d0d-108">Pianificazione da utilizzare nei valori di campionamento.</span><span class="sxs-lookup"><span data-stu-id="43d0d-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="43d0d-109">valori:' t []</span><span class="sxs-lookup"><span data-stu-id="43d0d-109">values : 'T[]</span></span>

<span data-ttu-id="43d0d-110">Matrice di valori da campionare.</span><span class="sxs-lookup"><span data-stu-id="43d0d-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="43d0d-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="43d0d-111">Output : 'T[]</span></span>

<span data-ttu-id="43d0d-112">Matrice di elementi dai valori, in base alla pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="43d0d-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="43d0d-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="43d0d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43d0d-114">T</span><span class="sxs-lookup"><span data-stu-id="43d0d-114">'T</span></span>


---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Sampled (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211628"
---
# <a name="sampled-function"></a><span data-ttu-id="b551b-102">Sampled (funzione)</span><span class="sxs-lookup"><span data-stu-id="b551b-102">Sampled function</span></span>

<span data-ttu-id="b551b-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b551b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b551b-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b551b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b551b-105">Esegue il campionamento di una matrice specificata, usando la pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="b551b-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b551b-106">Input</span><span class="sxs-lookup"><span data-stu-id="b551b-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="b551b-107">pianificazione: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b551b-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b551b-108">Pianificazione da utilizzare nei valori di campionamento.</span><span class="sxs-lookup"><span data-stu-id="b551b-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="b551b-109">valori:' t []</span><span class="sxs-lookup"><span data-stu-id="b551b-109">values : 'T[]</span></span>

<span data-ttu-id="b551b-110">Matrice di valori da campionare.</span><span class="sxs-lookup"><span data-stu-id="b551b-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="b551b-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="b551b-111">Output : 'T[]</span></span>

<span data-ttu-id="b551b-112">Matrice di elementi dai valori, in base alla pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="b551b-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b551b-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b551b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b551b-114">T</span><span class="sxs-lookup"><span data-stu-id="b551b-114">'T</span></span>


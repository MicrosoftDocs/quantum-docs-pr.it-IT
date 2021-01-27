---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Sampled (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854939"
---
# <a name="sampled-function"></a><span data-ttu-id="05c4e-102">Sampled (funzione)</span><span class="sxs-lookup"><span data-stu-id="05c4e-102">Sampled function</span></span>

<span data-ttu-id="05c4e-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="05c4e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="05c4e-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="05c4e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="05c4e-105">Esegue il campionamento di una matrice specificata, usando la pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="05c4e-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="05c4e-106">Input</span><span class="sxs-lookup"><span data-stu-id="05c4e-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="05c4e-107">pianificazione: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="05c4e-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="05c4e-108">Pianificazione da utilizzare nei valori di campionamento.</span><span class="sxs-lookup"><span data-stu-id="05c4e-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="05c4e-109">valori:' t []</span><span class="sxs-lookup"><span data-stu-id="05c4e-109">values : 'T[]</span></span>

<span data-ttu-id="05c4e-110">Matrice di valori da campionare.</span><span class="sxs-lookup"><span data-stu-id="05c4e-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="05c4e-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="05c4e-111">Output : 'T[]</span></span>

<span data-ttu-id="05c4e-112">Matrice di elementi dai valori, in base alla pianificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="05c4e-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="05c4e-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="05c4e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="05c4e-114">T</span><span class="sxs-lookup"><span data-stu-id="05c4e-114">'T</span></span>


---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211968"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="471a1-102">CombinedStructure (funzione)</span><span class="sxs-lookup"><span data-stu-id="471a1-102">CombinedStructure function</span></span>

<span data-ttu-id="471a1-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="471a1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="471a1-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="471a1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="471a1-105">Dato uno o più livelli di rotazioni controllate, restituisce un singolo livello con indice di parametri del modello spostato in modo che i livelli distinti siano parametrizzati da parametri di modello distinti.</span><span class="sxs-lookup"><span data-stu-id="471a1-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="471a1-106">Input</span><span class="sxs-lookup"><span data-stu-id="471a1-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="471a1-107">livelli: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="471a1-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="471a1-108">Livelli da combinare.</span><span class="sxs-lookup"><span data-stu-id="471a1-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="471a1-109">Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="471a1-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="471a1-110">Un singolo livello di rotazioni controllate, che rappresenta la concatenazione di tutti gli altri livelli.</span><span class="sxs-lookup"><span data-stu-id="471a1-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>
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
# <a name="combinedstructure-function"></a>CombinedStructure (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dato uno o più livelli di rotazioni controllate, restituisce un singolo livello con indice di parametri del modello spostato in modo che i livelli distinti siano parametrizzati da parametri di modello distinti.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Input

### <a name="layers--controlledrotation"></a>livelli: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Livelli da combinare.



## <a name="output--controlledrotation"></a>Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Un singolo livello di rotazioni controllate, che rappresenta la concatenazione di tutti gli altri livelli.
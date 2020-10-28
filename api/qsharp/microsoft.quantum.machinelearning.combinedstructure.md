---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720519"
---
# <a name="combinedstructure-function"></a>CombinedStructure (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Dato uno o più livelli di rotazioni controllate, restituisce un singolo livello con indice di parametri del modello spostato in modo che i livelli distinti siano parametrizzati da parametri di modello distinti.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Input

### <a name="layers--controlledrotation"></a>livelli: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Livelli da combinare.



## <a name="output--controlledrotation"></a>Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Un singolo livello di rotazioni controllate, che rappresenta la concatenazione di tutti gli altri livelli.
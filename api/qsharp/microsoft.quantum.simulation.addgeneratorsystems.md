---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: d6e8f7085cf0558960d055dbeeb08740c3fab049
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229665"
---
# <a name="addgeneratorsystems-function"></a>AddGeneratorSystems (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aggiunge due oggetti `GeneratorSystem` per creare un nuovo oggetto `GeneratorSystem` .

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="generatorsystema--generatorsystem"></a>generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Primo oggetto `GeneratorSystem`.


### <a name="generatorsystemb--generatorsystem"></a>generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Secondo oggetto `GeneratorSystem`.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Oggetto `GeneratorSystem` che rappresenta un sistema che rappresenta la somma dei sistemi del generatore di input.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
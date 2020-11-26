---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 28e3c12d0ae0b08fc368c25eeb6f38d2834ca912
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229308"
---
# <a name="getgeneratorsystemfunction-function"></a>GetGeneratorSystemFunction (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Recupera la `GeneratorIndex` funzione in un oggetto `GeneratorSystem` .

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a>Input

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

La classe `GeneratorSystem` di interesse.



## <a name="output--int---generatorindex"></a>Output: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Funzione che indicizza ogni `GeneratorIndex` termine in un'Hamiltoniana.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
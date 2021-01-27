---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 7b6eabd203cecf8c64f0bff3e06f08a0bec31bf2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852762"
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
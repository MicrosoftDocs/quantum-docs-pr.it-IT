---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230583"
---
# <a name="interpolategeneratorsystems-function"></a>InterpolateGeneratorSystems (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un oggetto `TimeDependentGeneratorSystem` che rappresenta l'interpolazione lineare tra due oggetti `GeneratorSystem` .

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a>Input

### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Inizio `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Fine `GeneratorSystem` .



## <a name="output--timedependentgeneratorsystem"></a>Output: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)

Oggetto `TimeDependentGeneratorSystem` che rappresenta un sistema che rappresenta la somma dei sistemi del generatore di input, con peso $ (1-s) $ in `generatorSystemStart` e peso $s $ on `generatorSystemEnd` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [Microsoft. Quantum. Simulation. TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)
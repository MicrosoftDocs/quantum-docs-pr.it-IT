---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229155"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Moltiplica il coefficiente di tutti i termini in un oggetto `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="multiplier--double"></a>moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)

Moltiplicatore sul coefficiente.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Struttura `GeneratorSystem` da moltiplicare.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Oggetto `GeneratorSystem` che rappresenta un sistema con coefficienti di un fattore `multiplier` più grande.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
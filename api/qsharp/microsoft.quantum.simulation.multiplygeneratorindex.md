---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230447"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Moltiplica il coefficiente in un oggetto `GeneratorIndex` .

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Input

### <a name="multiplier--double"></a>moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)

Moltiplicatore sul coefficiente.


### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Struttura `GeneratorIndex` da moltiplicare.



## <a name="output--generatorindex"></a>Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Oggetto `GeneratorIndex` che rappresenta un termine con un fattore più grande del coefficiente `multiplier` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
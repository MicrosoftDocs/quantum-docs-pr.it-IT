---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724493"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


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
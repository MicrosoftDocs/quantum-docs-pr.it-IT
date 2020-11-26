---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionEvolutionSet
title: JordanWignerFermionEvolutionSet (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 31218f88d1446c232290ac7695c1ae01efbe22ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224990"
---
# <a name="jordanwignerfermionevolutionset-function"></a>JordanWignerFermionEvolutionSet (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Rappresenta un generatore dinamico come un set di controlli simulabili e un'espansione in base a JordanWigner.

```qsharp
function JordanWignerFermionEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Output: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Oggetto `EvolutionSet` che esegue il mapping di un oggetto `GeneratorIndex` per la base JordanWigner a un oggetto ' EvolutionUnitary.
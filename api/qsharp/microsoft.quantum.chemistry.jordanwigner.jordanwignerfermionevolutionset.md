---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionEvolutionSet
title: JordanWignerFermionEvolutionSet (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 06dadc8e9b41302dcba99bd98e3744a1ab697ae6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838946"
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
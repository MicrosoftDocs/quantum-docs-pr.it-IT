---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722046"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un generatore dinamico come un set di porte simulabili e un'espansione in base a Pauli.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Output: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Oggetto `EvolutionSet` che esegue il mapping di un oggetto `GeneratorIndex` per la base di Pauli a un oggetto ' EvolutionUnitary.

## <a name="remarks"></a>Commenti

Questa operazione viene ottenuta dall'applicazione parziale di <xref:microsoft.quantum.simulation.paulievolutionfunction> .
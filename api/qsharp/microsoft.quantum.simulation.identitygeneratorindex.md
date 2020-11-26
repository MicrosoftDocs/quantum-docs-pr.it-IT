---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229291"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un indice del generatore coerente con l'Hamiltoniana zero, `H = 0` , che corrisponde all'operazione di evoluzione dell'identità.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Input

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.simulation.generatorsystem> tipo definito dall'utente.



## <a name="output--generatorindex"></a>Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indice del generatore che rappresenta l'evoluzione sotto la $H hamiltoniana = $0.
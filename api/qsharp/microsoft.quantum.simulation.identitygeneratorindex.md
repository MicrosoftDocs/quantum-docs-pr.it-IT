---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724538"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Restituisce un indice del generatore coerente con l'Hamiltoniana zero, `H = 0` , che corrisponde all'operazione di evoluzione dell'identità.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Input

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.simulation.generatorsystem> tipo definito dall'utente.



## <a name="output--generatorindex"></a>Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indice del generatore che rappresenta l'evoluzione sotto la $H hamiltoniana = $0.
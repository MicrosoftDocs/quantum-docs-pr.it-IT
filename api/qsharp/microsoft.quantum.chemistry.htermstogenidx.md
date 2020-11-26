---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216014"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Converte un indice in un termine hamiltoniana in `HTerm[]` formato dati in un GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Input

### <a name="data--hterm"></a>dati: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Dati di input nel `HTerm[]` formato.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Informazioni aggiuntive aggiunte a GeneratorIndex.


### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Indicizzare un termine dell'Hamiltoniana



## <a name="output--generatorindex"></a>Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Oggetto GeneratorIndex che rappresenta un termine hamiltoniana rappresentato da `data[idx]` , insieme alle informazioni aggiuntive aggiunte da `termType` .
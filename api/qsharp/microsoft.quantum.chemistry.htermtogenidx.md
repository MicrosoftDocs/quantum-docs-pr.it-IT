---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839612"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Converte un termine hamiltoniana in `HTerm` formato dati in un GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Input

### <a name="term--hterm"></a>termine: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Dati di input nel `HTerm` formato.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Informazioni aggiuntive aggiunte a GeneratorIndex.



## <a name="output--generatorindex"></a>Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Oggetto GeneratorIndex che rappresenta un termine hamiltoniana rappresentato da `term` , insieme alle informazioni aggiuntive aggiunte da `termType` .
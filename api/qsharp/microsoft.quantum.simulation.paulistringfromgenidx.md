---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230311"
---
# <a name="paulistringfromgenidx-function"></a>PauliStringFromGenIdx (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Estrae la stringa Pauli e i relativi indici qubit di un termine di Pauli descritto da un oggetto `GeneratorIndex` .

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a>Input

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` tipo che codifica un termine di Pauli.



## <a name="output--pauliint"></a>Output: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])

Stringa di Pauli del termine descritta da un oggetto `GeneratorIndex` e indici per il qubits su cui agisce.
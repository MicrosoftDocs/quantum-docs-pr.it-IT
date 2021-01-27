---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operazione ApplyMultiplyControlledLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841667"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>Operazione ApplyMultiplyControlledLowDepthAnd

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa un controllo Toffoli a più controlli, supponendo che la destinazione qubit sia inizializzata su 0.  L'operazione contigua presuppone che il qubit di destinazione verrà reimpostato su 0.  Richiede una profondità RZ di 1, mentre il numero di qubits Helper è esponenziale nel numero di qubits.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>Input

### <a name="controls--qubit"></a>Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits di controllo


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di destinazione



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


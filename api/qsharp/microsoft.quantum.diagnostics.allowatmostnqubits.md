---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operazione AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830908"
---
# <a name="allowatmostnqubits-operation"></a>Operazione AllowAtMostNQubits

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tra una chiamata a questa operazione e la relativa contigua, asserisce che al massimo un determinato numero di qubits aggiuntivi viene allocato con istruzioni using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero massimo di qubits che possono essere allocati.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da visualizzare in caso di errore.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

Il frammento di codice seguente avrà esito negativo quando viene eseguito nei computer che supportano questa diagnostica:

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a>Commenti

Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.
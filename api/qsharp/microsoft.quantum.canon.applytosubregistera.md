---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Operazione ApplyToSubregisterA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717027"
---
# <a name="applytosubregistera-operation"></a>Operazione ApplyToSubregisterA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.
Il modificatore `A` indica che l'operazione è adjointable.

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare al sottoregistro.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di indici, che indica a quale qubits verrà applicata l'operazione.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro in cui viene eseguita l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
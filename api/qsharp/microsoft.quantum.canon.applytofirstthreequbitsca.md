---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: Operazione ApplyToFirstThreeQubitsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 7e090a116a63e26278b05dc7c2fda9b65ff15bae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208789"
---
# <a name="applytofirstthreequbitsca-operation"></a>Operazione ApplyToFirstThreeQubitsCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione ai primi tre qubits nel registro.
Il modificatore `CA` indica che l'operazione è controllabile e adjointable.

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da applicare ai primi tre qubits


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit per le prime tre qubits di cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivale a:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)
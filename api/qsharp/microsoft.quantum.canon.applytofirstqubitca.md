---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operazione ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717394"
---
# <a name="applytofirstqubitca-operation"></a>Operazione ApplyToFirstQubitCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica Operation op al primo qubit nel registro.
Il modificatore `CA` indica che l'operazione è controllabile e adjointable.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-adj--ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) di registrazione e CTL

Operazione da applicare al primo qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit per la prima qubit di cui viene applicata l'operazione



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
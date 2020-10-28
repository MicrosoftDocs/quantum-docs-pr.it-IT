---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operazione ApplyToFirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717408"
---
# <a name="applytofirstqubitc-operation"></a>Operazione ApplyToFirstQubitC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica Operation op al primo qubit nel registro.
Il modificatore `C` indica che l'operazione è controllabile.

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL

Operazione da applicare al primo qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit per la prima qubit di cui viene applicata l'operazione



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
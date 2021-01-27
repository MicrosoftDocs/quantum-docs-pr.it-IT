---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operazione ApplyIfC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841850"
---
# <a name="applyifc-operation"></a>Operazione ApplyIfC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione controllabile condizionata su un bit classico.

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a>Descrizione

Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` . Se `false` , non viene eseguita alcuna operazione in `target` .
Il suffisso `C` indica che l'operazione da applicare è controllabile.

## <a name="input"></a>Input

### <a name="op--t--unit--is-ctl"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Operazione da applicare in modo condizionale.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

valore booleano che controlla se op viene applicato o meno.


### <a name="target--t"></a>destinazione:' t

Input a cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da applicare in modo condizionale.

## <a name="example"></a>Esempio

Il codice seguente prepara un registro di qubits in uno stato di base computazionale rappresentato da una stringa di bit classica specificata come matrice di `Bool` valori:

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)
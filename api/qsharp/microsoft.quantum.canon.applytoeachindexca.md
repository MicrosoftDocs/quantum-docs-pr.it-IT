---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operazione ApplyToEachIndexCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850793"
---
# <a name="applytoeachindexca-operation"></a>Operazione ApplyToEachIndexCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica una singola operazione qubit a ogni elemento indicizzato in un registro.
Il modificatore `CA` indica che l'operazione Single-qubit è adjointable e controllabile.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da applicare a ogni qubit.


### <a name="register--t"></a>registra:' t []

Matrice di qubits su cui applicare l'operazione specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui viene eseguita ciascuna operazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
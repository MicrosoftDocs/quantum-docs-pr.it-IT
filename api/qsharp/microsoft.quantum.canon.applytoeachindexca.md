---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operazione ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717517"
---
# <a name="applytoeachindexca-operation"></a>Operazione ApplyToEachIndexCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una singola operazione qubit a ogni elemento indicizzato in un registro.
Il modificatore `CA` indica che l'operazione Single-qubit è adjointable e controllabile.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="singleelementoperation--intt--unit-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione da applicare a ogni qubit.


### <a name="register--t"></a>registra:' t []

Matrice di qubits su cui applicare l'operazione specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui viene eseguita ciascuna operazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
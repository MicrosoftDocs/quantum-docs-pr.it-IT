---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operazione ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717590"
---
# <a name="applytoeach-operation"></a>Operazione ApplyToEach

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione Single-qubit a ogni elemento in un registro.

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="singleelementoperation--t--unit"></a>singleElementOperation:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da applicare a ogni qubit.


### <a name="register--t"></a>registra:' t []

Matrice di qubits su cui applicare l'operazione specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione su cui agisce l'operazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. Quantum. Canon. ApplyToEachA](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. Quantum. Canon. ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
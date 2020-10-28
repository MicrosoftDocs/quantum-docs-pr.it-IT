---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operazione ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717562"
---
# <a name="applytoeachc-operation"></a>Operazione ApplyToEachC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione Single-qubit a ogni elemento in un registro.
Il modificatore `C` indica che l'operazione Single-qubit è controllabile.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="singleelementoperation--t--unit-ctl"></a>singleElementOperation:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Operazione da applicare a ogni qubit.


### <a name="register--t"></a>registra:' t []

Matrice di qubits su cui applicare l'operazione specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione su cui agisce l'operazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
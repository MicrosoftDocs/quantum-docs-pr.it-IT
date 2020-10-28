---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operazione ApplyToEachIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717545"
---
# <a name="applytoeachindex-operation"></a>Operazione ApplyToEachIndex

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una singola operazione qubit a ogni elemento indicizzato in un registro.

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione da applicare a ogni qubit.


### <a name="register--t"></a>registra:' t []

Matrice di qubits su cui applicare l'operazione specificata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui viene eseguita ciascuna operazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Microsoft. Quantum. Canon. ApplyToEachIndexA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Microsoft. Quantum. Canon. ApplyToEachIndexC](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Microsoft. Quantum. Canon. ApplyToEachIndexCA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)
---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operazione SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724675"
---
# <a name="settobasisstate-operation"></a>Operazione SetToBasisState

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto [](https://nuget.org/packages/)


Imposta un qubit su uno stato di base di calcolo specificato misurando il qubit e applicando un flip di bit se necessario.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="desired--__invalidresult__"></a>desiderato: __non <Result> valido__

Stato di base su cui deve essere impostato qubit.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di cui è necessario impostare lo stato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Come invariante di questa operazione, la chiamata `M(q)` immediata dopo `SetToBasisState(result, q)` restituirà `result` .
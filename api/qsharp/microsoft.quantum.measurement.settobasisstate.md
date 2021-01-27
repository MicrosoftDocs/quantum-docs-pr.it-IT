---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operazione SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854616"
---
# <a name="settobasisstate-operation"></a>Operazione SetToBasisState

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
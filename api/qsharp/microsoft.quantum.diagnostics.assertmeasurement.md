---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operazione AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713037"
---
# <a name="assertmeasurement-operation"></a>Operazione AssertMeasurement

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Le asserzioni che misurano il qubits specificato in base a Pauli specificato avranno sempre il risultato specificato.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a>Input

### <a name="bases--pauli"></a>basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un effetto di misura per dichiarare la probabilità di, espressa come un operatore Pauli multiqubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro in cui eseguire l'asserzione.


### <a name="result--__invalidresult__"></a>risultato: __non <Result> valido__

Risultato previsto di `Measure(bases, qubits)` .


### <a name="msg--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da segnalare se l'asserzione ha esito negativo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Si noti che le versioni adiacenti e controllate di questa operazione non verificheranno la condizione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)
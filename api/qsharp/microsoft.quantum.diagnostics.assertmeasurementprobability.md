---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operazione AssertMeasurementProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830828"
---
# <a name="assertmeasurementprobability-operation"></a>Operazione AssertMeasurementProbability

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Le asserzioni che misurano il qubits specificato in base a Pauli specificato avranno il risultato specificato con la probabilità specificata, entro una certa tolleranza.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="bases--pauli"></a>basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un effetto di misura per dichiarare la probabilità di, espressa come un operatore Pauli multiqubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro in cui eseguire l'asserzione.


### <a name="result--__invalidresult__"></a>risultato: __non <Result> valido__

Risultato previsto di `Measure(bases, qubits)` .


### <a name="prob--double"></a>Probe: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilità con cui è previsto il risultato specificato.


### <a name="msg--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da segnalare se l'asserzione ha esito negativo.


### <a name="tol--double"></a>Tol: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a>Commenti

Si noti che le versioni adiacenti e controllate di questa operazione non verificheranno la condizione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)
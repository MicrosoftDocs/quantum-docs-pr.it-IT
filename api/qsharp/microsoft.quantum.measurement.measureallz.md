---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operazione MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854682"
---
# <a name="measureallz-operation"></a>Operazione MeasureAllZ

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misura in modo comune un registro di qubits in base a Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Descrizione

Misura un registro di qubits nel $Z \otimes Z \otimes \cdots \otimes Z $, che rappresenta la parità dell'intero registro.

## <a name="input"></a>Input

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato della misurazione $Z \otimes Z \otimes \cdots \otimes Z $.
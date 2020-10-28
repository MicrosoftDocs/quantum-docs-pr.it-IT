---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operazione MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711077"
---
# <a name="measureallz-operation"></a>Operazione MeasureAllZ

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto [](https://nuget.org/packages/)


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
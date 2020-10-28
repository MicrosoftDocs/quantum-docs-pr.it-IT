---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operazione EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712396"
---
# <a name="encodeintofivequbitcode-operation"></a>Operazione EncodeIntoFiveQubitCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Codifica nel codice Quantum ⟧ ⟦ 5, 1, 3.

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Input

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit che rappresenta uno stato non codificato. Questa matrice `Qubit[]` è di lunghezza 1.


### <a name="auxqubits--qubit"></a>auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits ausiliario che verrà usato per rappresentare lo stato codificato.



## <a name="output--logicalregister"></a>Output: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits fisici di tipo `LogicalRegister` che archivia lo stato codificato.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operazione EncodeIntoBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712407"
---
# <a name="encodeintobitflipcode-operation"></a>Operazione EncodeIntoBitFlipCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Codifica nel codice [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip.

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Input

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits fisico che rappresenta i dati da proteggere.


### <a name="auxqubits--qubit"></a>auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits ausiliario inizialmente nello stato $ \ket {00} $ da utilizzare per la codifica dei dati da proteggere.



## <a name="output--logicalregister"></a>Output: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Qubits fisico e ausiliario utilizzati nella codifica, rappresentati come registro logico.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
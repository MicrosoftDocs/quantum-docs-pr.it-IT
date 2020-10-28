---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Operazione DecodeFromFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712466"
---
# <a name="decodefromfivequbitcode-operation"></a>Operazione DecodeFromFiveQubitCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Decodifica il codice Quantum ⟧ ⟦ 5, 1, 3.

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Input

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits che rappresenta lo stato logico del codice 5 qubit codificato.



## <a name="output--qubitqubit"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Matrice qubit di lunghezza 1 che rappresenta lo stato non codificato nel primo parametro, insieme al qubits ausiliario nel secondo parametro.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. FiveQubitCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
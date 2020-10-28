---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Operazione DecodeFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712421"
---
# <a name="decodefromsteanecode-operation"></a>Operazione DecodeFromSteaneCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Operazione di codifica inversa che esegue il mapping di un registro quantum non codificato a un registro Quantum codificato nel codice quantico ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Input

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits che rappresenta lo stato logico del codice 5 qubit codificato.



## <a name="output--qubitqubit"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Matrice qubit di lunghezza 1 che rappresenta lo stato non codificato nel primo parametro, insieme al qubits ausiliario nel secondo parametro.

## <a name="remarks"></a>Commenti

Il decodificatore scelto usa la proprietà del codice CSS del codice Steane ⟧ ⟦ 7, 1, 3, ovvero corregge gli errori X e Z separatamente. Una proprietà del codice è che la posizione della X, rispettivamente, della correzione Z da applicare è la codifica a 3 bit della sindrome X, rispettivamente, Z quando viene considerato un numero intero.

## <a name="references"></a>Riferimenti

- D. Gottesman, "codici stabilizzatori e correzione errori Quantum", Ph.D. tesi, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operazione EncodeIntoSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712393"
---
# <a name="encodeintosteanecode-operation"></a>Operazione EncodeIntoSteaneCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Operazione di codifica che esegue il mapping di un registro quantum non codificato a un registro Quantum codificato nel codice Quantum ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Input

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit che include lo stato quantum non codificato


### <a name="auxqubits--qubit"></a>auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit inizialmente zero e che viene aggiunto al sistema Quantum in modo che sia possibile eseguire un'operazione di codifica



## <a name="output--logicalregister"></a>Output: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Registro Quantum che contiene lo stato dopo l'applicazione del codificatore Steane

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operazione AssertAllZeroWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713040"
---
# <a name="assertallzerowithintolerance-operation"></a>Operazione AssertAllZeroWithinTolerance

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiarare che i qubits specificati sono tutti nello stato $ \ket {0} $ fino a una determinata tolleranza.

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a>Input

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits che vengono dichiarati come nello stato $ \ket {0} $.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Accuratezza con cui lo stato deve essere nello stato di $ \ket {0} $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)
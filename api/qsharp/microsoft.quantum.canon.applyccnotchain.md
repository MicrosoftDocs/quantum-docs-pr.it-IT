---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Operazione ApplyCCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845131"
---
# <a name="applyccnotchain-operation"></a>Operazione ApplyCCNOTChain

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa una cascata di controlli CCNOT controllati sui bit corrispondenti di due registri qubit, agendo sul qubit successivo di uno dei registri.
A partire da qubits nella posizione 0 in entrambi i registri come controlli, CCNOT viene applicato a qubit nella posizione 1 del registro di destinazione, quindi controllato da qubits nella posizione 1 che agisce su qubit nella posizione 2 nel registro di destinazione e così via, terminando con un'azione sul qubit di destinazione in posizione `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit Register, usato solo per i controlli.


### <a name="targets--qubit"></a>destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit, usato per i controlli e come destinazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Il registro qubit di destinazione deve avere un qubit maggiore di quello dell'altro.
---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operazione ApplyMultiControlledC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218411"
---
# <a name="applymulticontrolledc-operation"></a>Operazione ApplyMultiControlledC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica una versione controllata multipla di un'operazione controllata singolarmente.
Il modificatore `C` indica che l'operazione Single-qubit è controllabile.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Input

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione controllata in un singolo qubit.
Si presuppone che il primo qubit nell'argomento dell'operazione sia un controllo e che si presuppone che il resto sia qubits di destinazione.
`ApplyMultiControlled` chiama sempre `singlyControlledOp` con un argomento di lunghezza almeno 1.


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Controllo non controllato da utilizzare per la costruzione.


### <a name="controls--qubit"></a>Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits da `singlyControlledOp` controllare.
La lunghezza di `controls` deve essere almeno 1.


### <a name="targets--qubit"></a>destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits di destinazione che `singlyControlledOp` agisce su.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione usa solo ancilla qubits puliti.

Per la spiegazione e il diagramma di circuito, vedere la figura 4,10, sezione 4,3 in Nielsen & Chuang

## <a name="references"></a>Riferimenti

- [*Michael A. Nielsen, Isaac L. Chuang*, quantum computing e Quantum Information](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)
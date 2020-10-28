---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operazione ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717965"
---
# <a name="applymulticontrolledca-operation"></a>Operazione ApplyMultiControlledCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una versione controllata multipla di un'operazione controllata singolarmente.
Il modificatore `CA` indica che l'operazione Single-qubit è controllabile e adjointable.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione controllata in un singolo qubit.
Il primo qubit nell'argomento dell'operazione presuppone che sia un controllo e che si presuppone che il resto sia qubits di destinazione.
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

- [*Michael A. Nielsen, Isaac L. Chuang* , quantum computing e Quantum Information](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)
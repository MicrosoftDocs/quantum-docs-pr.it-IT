---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operazione AndLadder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 2c6114ec8a5caabdeea8ab7e26a4877e1633671c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209724"
---
# <a name="andladder-operation"></a>Operazione AndLadder

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue una "e una scala" controllata in un registro di qubits di destinazione.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Descrizione

Questa operazione applica una trasformazione descritta dal mapping seguente di base di calcolo, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ dove $ \ket{x \_ 1, \dots, x \_ n} $ si riferisce agli Stati di base computazionale di `controls` e dove $ \ket{y \_ 1, \dots, y \_ {n-1}} $ fa riferimento agli Stati di base di calcolo di `targets` .

## <a name="input"></a>Input

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Controllo CCNOT da utilizzare per la costruzione.


### <a name="controls--qubit"></a>Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits da usare come controlli per la scala e.
Questa operazione lascia gli Stati di base computazionale di `controls` invariante.
La lunghezza di `controls` deve essere almeno 2 e deve essere uguale a uno più la lunghezza di `targets` .


### <a name="targets--qubit"></a>destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

La lunghezza di `targets` deve essere almeno 1 e uguale alla lunghezza di `controls` meno uno.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

- Utilizzato come parte di <xref:microsoft.quantum.canon.applymulticontrolledc> e <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Per la spiegazione e il diagramma di circuito, vedere la figura 4,10, sezione 4,3 in Nielsen & Chuang.

## <a name="references"></a>Riferimenti

- [*Michael A. Nielsen, Isaac L. Chuang*, quantum computing e Quantum Information](http://doi.org/10.1017/CBO9780511976667)
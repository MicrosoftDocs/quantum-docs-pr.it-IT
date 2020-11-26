---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: Operazione ApplyOpRepeatedlyOverCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: b7d401f323d7affc27697744bb659c687e252682
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209109"
---
# <a name="applyoprepeatedlyoverca-operation"></a>Operazione ApplyOpRepeatedlyOverCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica più volte la stessa operazione su un registro qubit.

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Un'operazione da applicare più volte nel registro qubit


### <a name="targets--int"></a>destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrici annidate che descrivono le destinazioni dell'op. Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit su cui agire.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
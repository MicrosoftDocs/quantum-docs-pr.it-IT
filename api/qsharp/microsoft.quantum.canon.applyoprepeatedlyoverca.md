---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: Operazione ApplyOpRepeatedlyOverCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 970acfbc63bc95542827988c5c81387e8812f289
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717825"
---
# <a name="applyoprepeatedlyoverca-operation"></a>Operazione ApplyOpRepeatedlyOverCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica più volte la stessa operazione su un registro qubit.

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-adj--ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Un'operazione da applicare più volte nel registro qubit


### <a name="targets--int"></a>destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrici annidate che descrivono le destinazioni dell'op. Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit su cui agire.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
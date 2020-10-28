---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operazione ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717828"
---
# <a name="applyoprepeatedlyoverc-operation"></a>Operazione ApplyOpRepeatedlyOverC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica più volte la stessa operazione su un registro qubit.

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Un'operazione da applicare più volte nel registro qubit


### <a name="targets--int"></a>destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrici annidate che descrivono le destinazioni dell'op. Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit su cui agire.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
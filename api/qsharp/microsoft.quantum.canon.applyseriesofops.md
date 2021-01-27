---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operazione ApplySeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841504"
---
# <a name="applyseriesofops-operation"></a>Operazione ApplySeriesOfOps

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="listofops--t--unit-"></a>listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) []

Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare. Vengono applicati in sequenza, l'indice più basso.


### <a name="targets--int"></a>destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrici annidate che descrivono le destinazioni dell'op. Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.


### <a name="register--t"></a>registra:' t []

Registro qubit su cui agire.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="example"></a>Esempio

Il codice seguente applica exp ([PauliX, Pauliy], 0,5) a qubits 0, 1//Then X a qubit 2 Let Ops = [Exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubit (X, _)]; Let indici = [[0, 1], [2]]; ApplySeriesOfOps (OPS, indici, qubitArray);

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)
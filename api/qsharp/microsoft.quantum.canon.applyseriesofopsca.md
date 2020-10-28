---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operazione ApplySeriesOfOpsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717632"
---
# <a name="applyseriesofopsca-operation"></a>Operazione ApplySeriesOfOpsCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice. (Contiguo + controllato)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Input

### <a name="listofops--t--unit-adj--ctl"></a>listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []

Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare. Vengono applicati in sequenza, l'indice più basso.
Ogni deve avere un Funct e un functor controllato.


### <a name="targets--int"></a>destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrici annidate che descrivono le destinazioni dell'op. Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.


### <a name="register--t"></a>registra:' t []

Registro qubit su cui agire.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)
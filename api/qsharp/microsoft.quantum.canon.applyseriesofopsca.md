---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operazione ApplySeriesOfOpsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217884"
---
# <a name="applyseriesofopsca-operation"></a>Operazione ApplySeriesOfOpsCA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice. (Contiguo + controllato)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="listofops--t--unit--is-adj--ctl"></a>listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []

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
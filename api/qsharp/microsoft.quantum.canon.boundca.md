---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716635"
---
# <a name="boundca-function"></a>BoundCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.
Il modificatore `CA` indica che tutte le operazioni nella matrice sono adjointable e controllabili.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="operations--t--unit-adj--ctl"></a>operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []

Sequenza di operazioni da eseguire su un input specificato.



## <a name="output--t--unit-adj--ctl"></a>Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui ogni operazione nell'array agisce.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
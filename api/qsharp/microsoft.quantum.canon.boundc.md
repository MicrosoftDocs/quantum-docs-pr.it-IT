---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716666"
---
# <a name="boundc-function"></a>BoundC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.
Il modificatore `C` indica che tutte le operazioni nella matrice sono controllabili.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="operations--t--unit-ctl"></a>operazioni:' t = [unità](xref:microsoft.quantum.lang-ref.unit) di> CTL []

Sequenza di operazioni da eseguire su un input specificato.



## <a name="output--t--unit-ctl"></a>Output:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui ogni operazione nell'array agisce.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
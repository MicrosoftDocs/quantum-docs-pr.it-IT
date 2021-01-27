---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841040"
---
# <a name="boundc-function"></a>BoundC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.
Il modificatore `C` indica che tutte le operazioni nella matrice sono controllabili.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="operations--t--unit--is-ctl"></a>operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL []

Sequenza di operazioni da eseguire su un input specificato.



## <a name="output--t--unit--is-ctl"></a>Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL

Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui ogni operazione nell'array agisce.

## <a name="example"></a>Esempio

Gli elementi seguenti sono equivalenti:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

e

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
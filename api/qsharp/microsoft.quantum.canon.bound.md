---
uid: Microsoft.Quantum.Canon.Bound
title: Funzione associata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716705"
---
# <a name="bound-function"></a>Funzione associata

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di operazioni che operano su un singolo input, produce una nuova operazione che esegue ogni operazione specificata in sequenza.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Input

### <a name="operations--t--unit-"></a>operazioni:' t => [unità](xref:microsoft.quantum.lang-ref.unit) []

Sequenza di operazioni da eseguire su un input specificato.



## <a name="output--t--unit"></a>Output:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Nuova operazione che esegue ogni operazione specificata in sequenza sul relativo input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Destinazione in cui ogni operazione nell'array agisce.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. Bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)
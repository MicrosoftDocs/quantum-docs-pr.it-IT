---
uid: Microsoft.Quantum.Canon.Bound
title: Funzione associata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841057"
---
# <a name="bound-function"></a>Funzione associata

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Esempio

Gli elementi seguenti sono equivalenti:

```qsharp
let bound = Bound([U, V]);
bound(x);
```

e

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. Bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)
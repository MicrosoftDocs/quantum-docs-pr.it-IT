---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231093"
---
# <a name="integerbits-function"></a>IntegerBits (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce tutte le posizioni in cui vengono impostati i bit di un Integer.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Input

### <a name="value--int"></a>valore: [int](xref:microsoft.quantum.lang-ref.int)

Numero non negativo.


### <a name="length--int"></a>Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)

Numero di bit nell'espansione binaria di `value` .



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice che contiene tutte le posizioni di bit (a partire da 0) che sono 1 nell'espansione binaria, `value` considerando tutti i bit fino alla posizione `length - 1` .  Tutte le posizioni vengono ordinate nella matrice in base alla posizione in ordine crescente.
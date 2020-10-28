---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719847"
---
# <a name="integerbits-function"></a>IntegerBits (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


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
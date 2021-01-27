---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855409"
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

## <a name="example"></a>Esempio

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```
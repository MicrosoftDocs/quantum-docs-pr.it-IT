---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funzione compressa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219754"
---
# <a name="zipped-function"></a>Funzione compressa

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Input

### <a name="left--t"></a>Left:' t []

Matrice contenente i valori per il primo elemento di ogni tupla.


### <a name="right--u"></a>Right:' U []

Matrice contenente i valori per il secondo elemento di ogni tupla.



## <a name="output--tu"></a>Output: (t,' U) []

Matrice contenente le coppie del form `(left[idx], right[idx])` per ciascuna `idx` . Se le due matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice di sinistra.
### <a name="u"></a>' U

Tipo degli elementi della matrice corretti.

## <a name="see-also"></a>Vedere anche

- [Microsoft.Quantum.Arrays.ZipPED3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. Arrays. decompresso](xref:Microsoft.Quantum.Arrays.Unzipped)
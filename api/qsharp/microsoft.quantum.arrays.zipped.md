---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funzione compressa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718710"
---
# <a name="zipped-function"></a>Funzione compressa

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
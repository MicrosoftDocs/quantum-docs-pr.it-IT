---
uid: Microsoft.Quantum.Arrays.Zip
title: Funzione zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718731"
---
# <a name="zip-function"></a>Funzione zip

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


> [!WARNING]
> Il file zip è stato deprecato. Usare invece <xref:Microsoft.Quantum.Arrays.Zipped>.

Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. Arrays. decompresso](xref:Microsoft.Quantum.Arrays.Unzipped)
---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718695"
---
# <a name="zipped3-function"></a>Zipped3 (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Date tre matrici, restituisce una nuova matrice di 3 tuple in modo che ogni tupla con 3 Tuple contenga un elemento da ogni matrice originale.

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Input

### <a name="first--t1"></a>primo:' t 1 []

Matrice contenente i valori per il primo elemento di ogni tupla.


### <a name="second--t2"></a>secondo:' t 2 []

Matrice contenente i valori per il secondo elemento di ogni tupla.


### <a name="third--t3"></a>terzo:' t 3 []

Matrice contenente i valori per il terzo elemento di ogni tupla.



## <a name="output--t1t2t3"></a>Output: (' t 1,' t 2,' t 3) []

Matrice contenente 3 tuple del form `(first[idx], second[idx], third[idx])` per ciascuna `idx` . Se le tre matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t1"></a>' T 1

Tipo dei primi elementi della matrice.
### <a name="t2"></a>T 2

Tipo di secondi elementi della matrice.
### <a name="t3"></a>' T 3

Tipo dei tre elementi della matrice.

## <a name="see-also"></a>Vedere anche

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
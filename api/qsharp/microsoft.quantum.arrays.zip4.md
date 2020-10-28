---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718698"
---
# <a name="zip4-function"></a>Zip4 (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


> [!WARNING]
> Zip4 è stato deprecato. Usare invece <xref:Microsoft.Quantum.Arrays.Zipped4>.

Date quattro matrici, restituisce una nuova matrice di 4 tuple in modo che ogni tupla a 4 elementi contenga un elemento da ogni matrice originale.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Input

### <a name="first--t1"></a>primo:' t 1 []

Matrice contenente i valori per il primo elemento di ogni tupla.


### <a name="second--t2"></a>secondo:' t 2 []

Matrice contenente i valori per il secondo elemento di ogni tupla.


### <a name="third--t3"></a>terzo:' t 3 []

Matrice contenente i valori per il terzo elemento di ogni tupla.


### <a name="fourth--t4"></a>quarto:' t 4 []

Matrice contenente i valori per il quarto elemento di ogni tupla.



## <a name="output--t1t2t3t4"></a>Output: (' t 1,' t 2,' t 3,' t 4) []

Matrice contenente 4 tuple del form `(first[idx], second[idx], third[idx], fourth[idx])` per ciascuna `idx` . Se le quattro matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t1"></a>' T 1

Tipo dei primi elementi della matrice.
### <a name="t2"></a>T 2

Tipo di secondi elementi della matrice.
### <a name="t3"></a>' T 3

Tipo dei tre elementi della matrice.
### <a name="t4"></a>' T 4

Tipo dei quarti elementi della matrice.

## <a name="see-also"></a>Vedere anche

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
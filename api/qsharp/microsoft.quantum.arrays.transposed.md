---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funzione trasposta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850942"
---
# <a name="transposed-function"></a>Funzione trasposta

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce la trasposta di una matrice rappresentata come matrice di matrici.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Descrizione

Input come $r \times c $ Matrix con $r $ Rows e $c $ Columns.  La matrice è basata su righe, ad esempio, `matrix[i][j]` accede all'elemento alla riga $i $ e alla colonna $j $.

Questa funzione restituisce la $c \times r $ Matrix che rappresenta la traspone della matrice di input.

## <a name="input"></a>Input

### <a name="matrix--t"></a>matrice:' t [] []

Tabella $r \times c $ Matrix basata su righe



## <a name="output--t"></a>Output:' t [] []

Transposed $c \times r $ Matrix

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `matrix` .

## <a name="example"></a>Esempio

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```
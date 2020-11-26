---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funzione trasposta
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219992"
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
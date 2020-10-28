---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funzione trasposta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718815"
---
# <a name="transposed-function"></a>Funzione trasposta

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846264"
---
# <a name="columnat-function"></a>ColumnAt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Estrae una colonna da una matrice.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrizione

Questa funzione estrae una colonna in una matrice in ordine di riga.
L'estrazione di una riga corrsponds nell'accesso agli elementi del primo indice e pertanto non richiede alcun ulteriore trattamento.

## <a name="input"></a>Input

### <a name="column--int"></a>colonna: [int](xref:microsoft.quantum.lang-ref.int)

Colonna della matrice


### <a name="matrix--t"></a>matrice:' t [] []

matrice bidimensionale in ordine per riga



## <a name="output--t"></a>Output:' t []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `matrix` .

## <a name="example"></a>Esempio

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. transposed](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)
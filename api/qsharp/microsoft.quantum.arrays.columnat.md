---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210099"
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

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. transposed](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)
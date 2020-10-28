---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719454"
---
# <a name="columnat-function"></a>ColumnAt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
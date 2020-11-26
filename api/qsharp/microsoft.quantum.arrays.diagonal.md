---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221539"
---
# <a name="diagonal-function"></a>Diagonal (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una matrice di elementi diagonali di una matrice bidimensionale

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrizione

Se la matrice bidimensionale non ha una forma quadrata, verrà restituita la diagonale sopra il numero minimo di righe e colonne.

## <a name="input"></a>Input

### <a name="matrix--t"></a>matrice:' t [] []

matrice bidimensionale in ordine per riga



## <a name="output--t"></a>Output:' t []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `matrix` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. transposed](xref:Microsoft.Quantum.Arrays.Transposed)
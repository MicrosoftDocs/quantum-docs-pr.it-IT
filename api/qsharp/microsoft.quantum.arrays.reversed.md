---
uid: Microsoft.Quantum.Arrays.Reversed
title: Funzione invertita
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220434"
---
# <a name="reversed-function"></a>Funzione invertita

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Creare una matrice che contiene gli stessi elementi di una matrice di input, ma in ordine inverso.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t []

Matrice i cui elementi devono essere copiati in ordine inverso.



## <a name="output--t"></a>Output:' t []

Matrice contenente gli elementi `array[Length(array) - 1]` . `array[0]`.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.
---
uid: Microsoft.Quantum.Arrays.Reversed
title: Funzione invertita
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718911"
---
# <a name="reversed-function"></a>Funzione invertita

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
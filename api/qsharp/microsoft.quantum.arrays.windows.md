---
uid: Microsoft.Quantum.Arrays.Windows
title: Funzione Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842203"
---
# <a name="windows-function"></a>Funzione Windows

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce tutte le sottomatrici consecutive di lunghezza `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descrizione

Questa funzione restituisce tutte le `n - size + 1` sottomatrici di lunghezza `size` nell'ordine, dove `n` è la lunghezza di `arr` .
Le prime sottomatrici sono `arr[0..size - 1], arr[1..size], arr[2..size + 1]` fino all'ultima sottomatrice `arr[n - size..n - 1]` .

Se `size <= 0` o `size > n` , viene restituita una matrice vuota.

## <a name="input"></a>Input

### <a name="size--int"></a>Dimensioni: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza delle sottomatrici.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi.



## <a name="output--t"></a>Output:' t [] []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```
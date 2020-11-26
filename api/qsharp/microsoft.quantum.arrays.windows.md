---
uid: Microsoft.Quantum.Arrays.Windows
title: Funzione Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219890"
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
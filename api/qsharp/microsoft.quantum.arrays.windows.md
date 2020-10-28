---
uid: Microsoft.Quantum.Arrays.Windows
title: Funzione Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718746"
---
# <a name="windows-function"></a>Funzione Windows

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
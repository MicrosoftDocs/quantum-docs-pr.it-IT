---
uid: Microsoft.Quantum.Arrays.Most
title: Funzione most
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718998"
---
# <a name="most-function"></a>Funzione most

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Crea una matrice uguale a una matrice di input, ad eccezione del fatto che l'ultimo elemento della matrice viene eliminato.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t []

Matrice il cui primo è costituito da un penultimo elemento per formare la matrice di output.



## <a name="output--t"></a>Output:' t []

Matrice contenente gli elementi `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.
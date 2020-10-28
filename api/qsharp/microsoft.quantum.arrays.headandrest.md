---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719178"
---
# <a name="headandrest-function"></a>HeadAndRest (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Restituisce una tupla del primo e di tutti gli elementi rimanenti della matrice.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Input

### <a name="array--a"></a>array:' A []

Matrice con almeno un elemento.



## <a name="output--aa"></a>Output: (' A,' A [])

Tupla del primo e di tutti gli elementi rimanenti della matrice.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="a"></a>' A

Tipo degli elementi della matrice.
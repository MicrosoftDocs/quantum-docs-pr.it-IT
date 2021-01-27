---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848555"
---
# <a name="headandrest-function"></a>HeadAndRest (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
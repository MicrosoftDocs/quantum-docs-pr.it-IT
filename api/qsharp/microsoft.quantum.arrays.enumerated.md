---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funzione enumerata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848132"
---
# <a name="enumerated-function"></a>Funzione enumerata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice, restituisce una nuova matrice contenente gli elementi della matrice originale insieme agli indici di ogni elemento.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Input

### <a name="array--telement"></a>matrice:' TElement []

Matrice i cui elementi devono essere enumerati.



## <a name="output--inttelement"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),' TElement) []

Nuova matrice contenente gli elementi della matrice originale insieme ai relativi indici.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="telement"></a>' TElement

Tipo di elementi della matrice.

## <a name="example"></a>Esempio

I `for` cicli seguenti sono equivalenti:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```
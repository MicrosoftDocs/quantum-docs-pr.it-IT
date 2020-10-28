---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funzione enumerata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719307"
---
# <a name="enumerated-function"></a>Funzione enumerata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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
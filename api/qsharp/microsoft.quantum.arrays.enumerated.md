---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funzione enumerata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221420"
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
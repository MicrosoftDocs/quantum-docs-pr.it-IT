---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719151"
---
# <a name="indexrange-function"></a>IndexRange (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice, restituisce un intervallo sugli indici di tale matrice, adatto per l'uso in un ciclo for.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Input

### <a name="array--telement"></a>matrice:' TElement []

Matrice per la quale deve essere restituito un intervallo di indici.



## <a name="output--range"></a>Output: [intervallo](xref:microsoft.quantum.lang-ref.range)

Un intervallo su tutti gli indici della matrice.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="telement"></a>' TElement

Tipo di elementi della matrice.
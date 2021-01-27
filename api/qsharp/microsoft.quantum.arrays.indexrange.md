---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845787"
---
# <a name="indexrange-function"></a>IndexRange (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Esempio

I `for` cicli seguenti sono equivalenti:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```
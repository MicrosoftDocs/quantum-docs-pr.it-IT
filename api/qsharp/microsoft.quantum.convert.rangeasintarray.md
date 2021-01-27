---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850096"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una matrice `arr` di numeri interi enumerati da Start.. passaggio... fine.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Input

### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)

Oggetto `Range` di valori `start..step..end` da convertire in una matrice.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Nuova matrice di numeri interi che corrisponde ai valori iterati da `range` .

## <a name="example"></a>Esempio

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```
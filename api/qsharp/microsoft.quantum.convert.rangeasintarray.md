---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214008"
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
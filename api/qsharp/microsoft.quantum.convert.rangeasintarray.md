---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713362"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Crea una matrice `arr` di numeri interi enumerati da Start.. passaggio... fine.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Input

### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)

Oggetto `Range` di valori `start..step..end` da convertire in una matrice.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Nuova matrice di numeri interi che corrisponde ai valori iterati da `range` .
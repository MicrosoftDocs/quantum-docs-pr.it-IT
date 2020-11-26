---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220417"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta una condizione in cui una matrice bidimensionale ha una forma rettangolare

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Descrizione

Questa funzione dichiara che ogni riga in una matrice ha la stessa lunghezza.

## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t [] []

Matrice bidimensionale di elementi


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da stampare se la matrice non è una matrice rettangolare



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `array` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)
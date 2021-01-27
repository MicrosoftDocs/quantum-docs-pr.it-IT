---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831109"
---
# <a name="rangestart-function"></a>RangeStart (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce il valore iniziale definito dell'intervallo specificato.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Input

### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore iniziale definito dell'intervallo specificato.

## <a name="remarks"></a>Commenti

Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.

Si noti che il valore iniziale definito di un intervallo è uguale al primo elemento della sequenza, a meno che l'intervallo non specifichi una sequenza vuota (ad esempio, 2. 1).
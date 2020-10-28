---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713166"
---
# <a name="rangestart-function"></a>RangeStart (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto [](https://nuget.org/packages/)


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
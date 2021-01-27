---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853607"
---
# <a name="rangestep-function"></a>RangeStep (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce il numero intero che specifica la modalità di calcolo del valore successivo di un intervallo.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Input

### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore del passaggio definito dell'intervallo specificato.

## <a name="remarks"></a>Commenti

Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.
---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713247"
---
# <a name="rangeend-function"></a>RangeEnd (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto [](https://nuget.org/packages/)


Restituisce il valore finale definito dell'intervallo specificato, che non è necessariamente l'ultimo elemento della sequenza.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Input

### <a name="range--range"></a>intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Valore finale definito dell'intervallo specificato.

## <a name="remarks"></a>Commenti

Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.

Si noti che il valore finale definito di un intervallo può differire dall'ultimo elemento nella sequenza specificata dall'intervallo. ad esempio, in un intervallo compreso tra 0.. 2... 5 l'ultimo elemento è 4, ma il valore finale è 5.
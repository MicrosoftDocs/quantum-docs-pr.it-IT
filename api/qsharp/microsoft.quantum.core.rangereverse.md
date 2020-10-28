---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713233"
---
# <a name="rangereverse-function"></a>RangeReverse (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto [](https://nuget.org/packages/)


Restituisce un nuovo intervallo che è l'inverso dell'intervallo di input.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Input

### <a name="r--range"></a>r: [intervallo](xref:microsoft.quantum.lang-ref.range)

Intervallo di input.



## <a name="output--range"></a>Output: [intervallo](xref:microsoft.quantum.lang-ref.range)

Nuovo intervallo che è l'inverso dell'intervallo specificato.

## <a name="remarks"></a>Commenti

Si noti che l'inverso di un intervallo non è semplicemente `end` .. `-step` .. `start` , perché l'ultimo elemento effettivo di un intervallo potrebbe non essere uguale a `end` .
---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853649"
---
# <a name="rangereverse-function"></a>RangeReverse (funzione)

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
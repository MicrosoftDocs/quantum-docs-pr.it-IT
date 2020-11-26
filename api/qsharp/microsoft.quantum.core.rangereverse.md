---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213838"
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
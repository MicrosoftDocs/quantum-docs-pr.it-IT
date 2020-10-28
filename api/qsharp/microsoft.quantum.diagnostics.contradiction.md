---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funzione di contraddizione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712869"
---
# <a name="contradiction-function"></a>Funzione di contraddizione

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che una condizione classica è false.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--bool"></a>effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)

Condizione da dichiarare.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia true.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. fact](xref:Microsoft.Quantum.Diagnostics.Fact)
---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funzione di contraddizione
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202142"
---
# <a name="contradiction-function"></a>Funzione di contraddizione

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
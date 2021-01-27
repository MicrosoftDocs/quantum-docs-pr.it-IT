---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funzione fact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853315"
---
# <a name="fact-function"></a>Funzione fact

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dichiara che una condizione classica è true.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--bool"></a>effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)

Condizione da dichiarare.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia false.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

Il seguente frammento di codice Q # avrà esito negativo:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. Contraddition](xref:Microsoft.Quantum.Diagnostics.Contradiction)
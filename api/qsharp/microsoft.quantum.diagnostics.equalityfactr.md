---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712743"
---
# <a name="equalityfactr-function"></a>EqualityFactR (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che una variabile di risultato classica presenta il valore previsto.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--__invalidresult__"></a>effettivo: __non <Result> valido__

Variabile da verificare.


### <a name="expected--__invalidresult__"></a>previsto: __non <Result> valido__

Valore previsto.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


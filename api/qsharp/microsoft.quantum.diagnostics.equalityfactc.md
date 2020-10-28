---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712785"
---
# <a name="equalityfactc-function"></a>EqualityFactC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che un numero complesso presenta il valore previsto.

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--complex"></a>effettivo: [complesso](xref:Microsoft.Quantum.Math.Complex)

Valore da verificare.


### <a name="expected--complex"></a>previsto: [complesso](xref:Microsoft.Quantum.Math.Complex)

Valore previsto.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


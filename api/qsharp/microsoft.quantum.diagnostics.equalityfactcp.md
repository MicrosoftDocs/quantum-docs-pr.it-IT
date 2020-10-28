---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712771"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che un numero complesso presenta il valore previsto.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--complexpolar"></a>valore effettivo: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valore da verificare.


### <a name="expected--complexpolar"></a>previsto: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valore previsto.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


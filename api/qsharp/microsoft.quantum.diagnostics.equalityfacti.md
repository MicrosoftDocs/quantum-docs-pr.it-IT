---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712760"
---
# <a name="equalityfacti-function"></a>EqualityFactI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che una variabile int classica presenta il valore previsto.

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--int"></a>effettivo: [int](xref:microsoft.quantum.lang-ref.int)

Numero da verificare.


### <a name="expected--int"></a>previsto: [int](xref:microsoft.quantum.lang-ref.int)

Valore previsto.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


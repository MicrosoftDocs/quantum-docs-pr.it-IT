---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712757"
---
# <a name="equalityfactl-function"></a>EqualityFactL (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dichiara che una variabile BigInt classica presenta il valore previsto.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--bigint"></a>effettivo: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numero da verificare.


### <a name="expected--bigint"></a>previsto: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valore previsto.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


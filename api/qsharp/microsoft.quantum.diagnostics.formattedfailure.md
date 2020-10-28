---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712676"
---
# <a name="formattedfailure-function"></a>FormattedFailure (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Funzione interna utilizzata per generare un errore con messaggi di errore significativi.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Input

### <a name="actual--t"></a>valore effettivo:' t




### <a name="expected--t"></a>previsto:' t




### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Questa funzione è progettata per essere emulata dai runtime di simulazione, in modo da consentire l'invio di contraddizioni formattate.
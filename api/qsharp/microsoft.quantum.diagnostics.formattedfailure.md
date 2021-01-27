---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828272"
---
# <a name="formattedfailure-function"></a>FormattedFailure (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definito dall'utente RequiresCapability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725137"
---
# <a name="requirescapability-user-defined-type"></a>Tipo definito dall'utente RequiresCapability

Spazio dei nomi: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)

Pacchetto [](https://nuget.org/packages/)


Attributo riconosciuto dal compilatore utilizzato per contrassegnare un oggetto chiamabile con le funzionalità di runtime richieste.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Elementi denominati

### <a name="level--string"></a>Livello: [stringa](xref:microsoft.quantum.lang-ref.string)

Nome del livello di funzionalità di runtime richiesto dall'oggetto chiamabile.
### <a name="reason--string"></a>Motivo: [stringa](xref:microsoft.quantum.lang-ref.string)

Descrizione del motivo per cui l'oggetto chiamabile richiede questa funzionalità di Runtime.

## <a name="remarks"></a>Commenti

Questo attributo viene aggiunto automaticamente a Callable dal compilatore, a meno che non esista già un'istanza di questo attributo nell'oggetto chiamabile. Non deve essere usato tranne nei rari casi in cui il compilatore non deduce correttamente la funzionalità richiesta.

Di seguito è riportato l'elenco dei nomi dei livelli di funzionalità, in ordine di aumento delle funzionalità o delle restrizioni di riduzione:

## `"BasicQuantumFunctionality"`

Impossibile confrontare i risultati della misurazione per verificarne l'uguaglianza.

## `"BasicMeasurementFeedback"`

I risultati della misurazione possono essere confrontati per verificarne l'uguaglianza solo nelle espressioni condizionali if-Statement nelle operazioni. Il blocco di un'istruzione If che dipende da un risultato non può contenere istruzioni set per variabili modificabili dichiarate all'esterno del blocco o istruzioni return.

## `"FullComputation"`

Nessuna restrizione di Runtime. Qualsiasi programma Q # può essere eseguito.
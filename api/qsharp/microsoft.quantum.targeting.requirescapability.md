---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definito dall'utente RequiresCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231008"
---
# <a name="requirescapability-user-defined-type"></a>Tipo definito dall'utente RequiresCapability

Spazio dei nomi: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definito dall'utente deprecato
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713275"
---
# <a name="deprecated-user-defined-type"></a>Tipo definito dall'utente deprecato

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto [](https://nuget.org/packages/)


Attributo riconosciuto dal compilatore utilizzato per contrassegnare un tipo o chiamarlo come deprecato.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Elementi denominati

### <a name="newname--string"></a>NewName: [stringa](xref:microsoft.quantum.lang-ref.string)

Nome completo del tipo o chiamabile da utilizzare.
Viene impostato sulla stringa vuota se un tipo o una chiamata richiamabile è stata deprecata senza sostituzione.
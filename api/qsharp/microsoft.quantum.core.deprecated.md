---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definito dall'utente deprecato
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224089"
---
# <a name="deprecated-user-defined-type"></a>Tipo definito dall'utente deprecato

Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Attributo riconosciuto dal compilatore utilizzato per contrassegnare un tipo o chiamarlo come deprecato.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Elementi denominati

### <a name="newname--string"></a>NewName: [stringa](xref:microsoft.quantum.lang-ref.string)

Nome completo del tipo o chiamabile da utilizzare.
Viene impostato sulla stringa vuota se un tipo o una chiamata richiamabile è stata deprecata senza sostituzione.
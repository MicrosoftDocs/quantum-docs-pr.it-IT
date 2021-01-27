---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definito dall'utente deprecato
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832076"
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
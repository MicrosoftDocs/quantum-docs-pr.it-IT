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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="d5ae8-102">Tipo definito dall'utente deprecato</span><span class="sxs-lookup"><span data-stu-id="d5ae8-102">Deprecated user defined type</span></span>

<span data-ttu-id="d5ae8-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="d5ae8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="d5ae8-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d5ae8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d5ae8-105">Attributo riconosciuto dal compilatore utilizzato per contrassegnare un tipo o chiamarlo come deprecato.</span><span class="sxs-lookup"><span data-stu-id="d5ae8-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="d5ae8-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="d5ae8-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="d5ae8-107">NewName: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d5ae8-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d5ae8-108">Nome completo del tipo o chiamabile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d5ae8-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="d5ae8-109">Viene impostato sulla stringa vuota se un tipo o una chiamata richiamabile è stata deprecata senza sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d5ae8-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>
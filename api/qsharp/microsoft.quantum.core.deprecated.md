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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="0ab7c-102">Tipo definito dall'utente deprecato</span><span class="sxs-lookup"><span data-stu-id="0ab7c-102">Deprecated user defined type</span></span>

<span data-ttu-id="0ab7c-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="0ab7c-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="0ab7c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ab7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ab7c-105">Attributo riconosciuto dal compilatore utilizzato per contrassegnare un tipo o chiamarlo come deprecato.</span><span class="sxs-lookup"><span data-stu-id="0ab7c-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="0ab7c-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="0ab7c-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="0ab7c-107">NewName: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0ab7c-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0ab7c-108">Nome completo del tipo o chiamabile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="0ab7c-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="0ab7c-109">Viene impostato sulla stringa vuota se un tipo o una chiamata richiamabile è stata deprecata senza sostituzione.</span><span class="sxs-lookup"><span data-stu-id="0ab7c-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>
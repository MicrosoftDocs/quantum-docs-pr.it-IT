---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funzione di contraddizione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712869"
---
# <a name="contradiction-function"></a><span data-ttu-id="125fb-102">Funzione di contraddizione</span><span class="sxs-lookup"><span data-stu-id="125fb-102">Contradiction function</span></span>

<span data-ttu-id="125fb-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="125fb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="125fb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="125fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="125fb-105">Dichiara che una condizione classica è false.</span><span class="sxs-lookup"><span data-stu-id="125fb-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="125fb-106">Input</span><span class="sxs-lookup"><span data-stu-id="125fb-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="125fb-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="125fb-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="125fb-108">Condizione da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="125fb-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="125fb-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="125fb-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="125fb-110">Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia true.</span><span class="sxs-lookup"><span data-stu-id="125fb-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="125fb-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="125fb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="125fb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="125fb-112">See Also</span></span>

- [<span data-ttu-id="125fb-113">Microsoft. Quantum. Diagnostics. fact</span><span class="sxs-lookup"><span data-stu-id="125fb-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)
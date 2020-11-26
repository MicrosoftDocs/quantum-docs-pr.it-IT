---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funzione di contraddizione
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202142"
---
# <a name="contradiction-function"></a><span data-ttu-id="a4278-102">Funzione di contraddizione</span><span class="sxs-lookup"><span data-stu-id="a4278-102">Contradiction function</span></span>

<span data-ttu-id="a4278-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a4278-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a4278-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a4278-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a4278-105">Dichiara che una condizione classica è false.</span><span class="sxs-lookup"><span data-stu-id="a4278-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a4278-106">Input</span><span class="sxs-lookup"><span data-stu-id="a4278-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="a4278-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a4278-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a4278-108">Condizione da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="a4278-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="a4278-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a4278-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a4278-110">Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia true.</span><span class="sxs-lookup"><span data-stu-id="a4278-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4278-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4278-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a4278-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4278-112">See Also</span></span>

- [<span data-ttu-id="a4278-113">Microsoft. Quantum. Diagnostics. fact</span><span class="sxs-lookup"><span data-stu-id="a4278-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)
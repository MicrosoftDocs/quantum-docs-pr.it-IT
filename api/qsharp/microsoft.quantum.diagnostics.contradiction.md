---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funzione di contraddizione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829357"
---
# <a name="contradiction-function"></a><span data-ttu-id="fa16f-102">Funzione di contraddizione</span><span class="sxs-lookup"><span data-stu-id="fa16f-102">Contradiction function</span></span>

<span data-ttu-id="fa16f-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fa16f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fa16f-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fa16f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fa16f-105">Dichiara che una condizione classica è false.</span><span class="sxs-lookup"><span data-stu-id="fa16f-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fa16f-106">Input</span><span class="sxs-lookup"><span data-stu-id="fa16f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="fa16f-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa16f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa16f-108">Condizione da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="fa16f-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="fa16f-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fa16f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fa16f-110">Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia true.</span><span class="sxs-lookup"><span data-stu-id="fa16f-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa16f-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa16f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="fa16f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa16f-112">Example</span></span>

<span data-ttu-id="fa16f-113">Il seguente codice Q # stamperà "Hello, World":</span><span class="sxs-lookup"><span data-stu-id="fa16f-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="fa16f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa16f-114">See Also</span></span>

- [<span data-ttu-id="fa16f-115">Microsoft. Quantum. Diagnostics. fact</span><span class="sxs-lookup"><span data-stu-id="fa16f-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)
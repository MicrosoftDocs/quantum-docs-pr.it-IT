---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funzione fact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853315"
---
# <a name="fact-function"></a><span data-ttu-id="17cea-102">Funzione fact</span><span class="sxs-lookup"><span data-stu-id="17cea-102">Fact function</span></span>

<span data-ttu-id="17cea-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="17cea-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="17cea-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="17cea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="17cea-105">Dichiara che una condizione classica è true.</span><span class="sxs-lookup"><span data-stu-id="17cea-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="17cea-106">Input</span><span class="sxs-lookup"><span data-stu-id="17cea-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="17cea-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="17cea-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="17cea-108">Condizione da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="17cea-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="17cea-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="17cea-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="17cea-110">Stringa del messaggio di errore da stampare nel caso in cui la condizione classica sia false.</span><span class="sxs-lookup"><span data-stu-id="17cea-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17cea-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17cea-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="17cea-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="17cea-112">Example</span></span>

<span data-ttu-id="17cea-113">Il seguente frammento di codice Q # avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="17cea-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="17cea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17cea-114">See Also</span></span>

- [<span data-ttu-id="17cea-115">Microsoft. Quantum. Diagnostics. Contraddition</span><span class="sxs-lookup"><span data-stu-id="17cea-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)
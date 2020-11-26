---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228866"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="90c79-102">WithZeroInsertedAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="90c79-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="90c79-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="90c79-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="90c79-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90c79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90c79-105">Inserire un valore a 0 bit in un Integer</span><span class="sxs-lookup"><span data-stu-id="90c79-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="90c79-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90c79-106">Description</span></span>

<span data-ttu-id="90c79-107">Questa operazione accetta un Integer, inserisce un oggetto a bit 0 `position` e restituisce il valore aggiornato come Integer.</span><span class="sxs-lookup"><span data-stu-id="90c79-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="90c79-108">Se, ad esempio, si inserisce un valore 0 nella posizione 2 nel numero 10 ($10 _ {10} = 1010_ {2} $), viene restituito il numero 18 ($ 18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="90c79-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="90c79-109">Input</span><span class="sxs-lookup"><span data-stu-id="90c79-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="90c79-110">Posizione: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90c79-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90c79-111">Posizione in cui viene inserito 0</span><span class="sxs-lookup"><span data-stu-id="90c79-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="90c79-112">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90c79-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90c79-113">Valore modificato</span><span class="sxs-lookup"><span data-stu-id="90c79-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="90c79-114">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90c79-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90c79-115">Valore modificato</span><span class="sxs-lookup"><span data-stu-id="90c79-115">Modified value</span></span>
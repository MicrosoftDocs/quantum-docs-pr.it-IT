---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855203"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="93452-102">WithZeroInsertedAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="93452-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="93452-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="93452-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="93452-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93452-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93452-105">Inserire un valore a 0 bit in un Integer</span><span class="sxs-lookup"><span data-stu-id="93452-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="93452-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93452-106">Description</span></span>

<span data-ttu-id="93452-107">Questa operazione accetta un Integer, inserisce un oggetto a bit 0 `position` e restituisce il valore aggiornato come Integer.</span><span class="sxs-lookup"><span data-stu-id="93452-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="93452-108">Se, ad esempio, si inserisce un valore 0 nella posizione 2 nel numero 10 ($10 _ {10} = 1010_ {2} $), viene restituito il numero 18 ($ 18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="93452-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="93452-109">Input</span><span class="sxs-lookup"><span data-stu-id="93452-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="93452-110">Posizione: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93452-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93452-111">Posizione in cui viene inserito 0</span><span class="sxs-lookup"><span data-stu-id="93452-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="93452-112">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93452-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93452-113">Valore modificato</span><span class="sxs-lookup"><span data-stu-id="93452-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="93452-114">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93452-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93452-115">Valore modificato</span><span class="sxs-lookup"><span data-stu-id="93452-115">Modified value</span></span>
---
uid: Microsoft.Quantum.Logical.Not
title: Not-funzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849085"
---
# <a name="not-function"></a><span data-ttu-id="7f45c-102">Not-funzione</span><span class="sxs-lookup"><span data-stu-id="7f45c-102">Not function</span></span>

<span data-ttu-id="7f45c-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7f45c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7f45c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f45c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f45c-105">Restituisce la negazione booleana di un valore.</span><span class="sxs-lookup"><span data-stu-id="7f45c-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="7f45c-106">Input</span><span class="sxs-lookup"><span data-stu-id="7f45c-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="7f45c-107">valore: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7f45c-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7f45c-108">Valore da negare.</span><span class="sxs-lookup"><span data-stu-id="7f45c-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7f45c-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7f45c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7f45c-110">`true` Se e solo se `value` è `false` .</span><span class="sxs-lookup"><span data-stu-id="7f45c-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f45c-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="7f45c-111">Remarks</span></span>

<span data-ttu-id="7f45c-112">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="7f45c-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```
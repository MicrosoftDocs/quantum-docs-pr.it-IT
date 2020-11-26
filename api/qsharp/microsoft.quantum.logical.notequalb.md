---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197382"
---
# <a name="notequalb-function"></a><span data-ttu-id="982e6-102">NotEqualB (funzione)</span><span class="sxs-lookup"><span data-stu-id="982e6-102">NotEqualB function</span></span>

<span data-ttu-id="982e6-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="982e6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="982e6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="982e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="982e6-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="982e6-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="982e6-106">Input</span><span class="sxs-lookup"><span data-stu-id="982e6-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="982e6-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="982e6-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="982e6-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="982e6-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="982e6-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="982e6-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="982e6-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="982e6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="982e6-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="982e6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="982e6-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="982e6-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="982e6-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="982e6-113">Remarks</span></span>

<span data-ttu-id="982e6-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="982e6-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```
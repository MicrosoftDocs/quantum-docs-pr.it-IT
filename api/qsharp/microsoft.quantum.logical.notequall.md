---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197229"
---
# <a name="notequall-function"></a><span data-ttu-id="f6582-102">NotEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="f6582-102">NotEqualL function</span></span>

<span data-ttu-id="f6582-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f6582-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f6582-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6582-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6582-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f6582-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="f6582-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6582-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f6582-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f6582-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f6582-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f6582-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f6582-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f6582-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f6582-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f6582-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f6582-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6582-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6582-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="f6582-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6582-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6582-113">Remarks</span></span>

<span data-ttu-id="f6582-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="f6582-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```
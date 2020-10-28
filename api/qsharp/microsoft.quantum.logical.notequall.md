---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709806"
---
# <a name="notequall-function"></a><span data-ttu-id="aef1b-102">NotEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="aef1b-102">NotEqualL function</span></span>

<span data-ttu-id="aef1b-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="aef1b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="aef1b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aef1b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aef1b-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="aef1b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="aef1b-106">Input</span><span class="sxs-lookup"><span data-stu-id="aef1b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="aef1b-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aef1b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aef1b-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="aef1b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="aef1b-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aef1b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aef1b-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="aef1b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="aef1b-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aef1b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aef1b-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="aef1b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="aef1b-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="aef1b-113">Remarks</span></span>

<span data-ttu-id="aef1b-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="aef1b-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```
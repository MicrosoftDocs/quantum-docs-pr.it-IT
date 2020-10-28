---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723474"
---
# <a name="notequald-function"></a><span data-ttu-id="f4c89-102">NotEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="f4c89-102">NotEqualD function</span></span>

<span data-ttu-id="f4c89-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4c89-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4c89-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4c89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4c89-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f4c89-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f4c89-106">Input</span><span class="sxs-lookup"><span data-stu-id="f4c89-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f4c89-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4c89-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4c89-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f4c89-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f4c89-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4c89-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4c89-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f4c89-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4c89-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4c89-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4c89-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="f4c89-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4c89-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f4c89-113">Remarks</span></span>

<span data-ttu-id="f4c89-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="f4c89-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```
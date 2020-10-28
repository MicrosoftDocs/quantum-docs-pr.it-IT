---
uid: Microsoft.Quantum.Arrays.Where
title: Funzione Where
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718755"
---
# <a name="where-function"></a><span data-ttu-id="f6c58-102">Funzione Where</span><span class="sxs-lookup"><span data-stu-id="f6c58-102">Where function</span></span>

<span data-ttu-id="f6c58-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f6c58-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f6c58-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6c58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6c58-105">Dato un predicato e una matrice, restituisce gli indici della matrice in cui il predicato è true.</span><span class="sxs-lookup"><span data-stu-id="f6c58-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f6c58-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6c58-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f6c58-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6c58-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6c58-108">Funzione da `'T` a booleana utilizzata per filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="f6c58-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f6c58-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="f6c58-109">array : 'T[]</span></span>

<span data-ttu-id="f6c58-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="f6c58-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="f6c58-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6c58-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f6c58-112">Matrice di indici in cui `predicate` è true.</span><span class="sxs-lookup"><span data-stu-id="f6c58-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f6c58-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f6c58-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6c58-114">T</span><span class="sxs-lookup"><span data-stu-id="f6c58-114">'T</span></span>

<span data-ttu-id="f6c58-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="f6c58-115">The type of `array` elements.</span></span>
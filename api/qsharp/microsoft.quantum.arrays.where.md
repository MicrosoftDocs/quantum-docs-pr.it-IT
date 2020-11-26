---
uid: Microsoft.Quantum.Arrays.Where
title: Funzione Where
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219924"
---
# <a name="where-function"></a><span data-ttu-id="cad05-102">Funzione Where</span><span class="sxs-lookup"><span data-stu-id="cad05-102">Where function</span></span>

<span data-ttu-id="cad05-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cad05-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cad05-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cad05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cad05-105">Dato un predicato e una matrice, restituisce gli indici della matrice in cui il predicato è true.</span><span class="sxs-lookup"><span data-stu-id="cad05-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="cad05-106">Input</span><span class="sxs-lookup"><span data-stu-id="cad05-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="cad05-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cad05-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cad05-108">Funzione da `'T` a booleana utilizzata per filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="cad05-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="cad05-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="cad05-109">array : 'T[]</span></span>

<span data-ttu-id="cad05-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="cad05-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="cad05-111">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cad05-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cad05-112">Matrice di indici in cui `predicate` è true.</span><span class="sxs-lookup"><span data-stu-id="cad05-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cad05-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="cad05-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cad05-114">T</span><span class="sxs-lookup"><span data-stu-id="cad05-114">'T</span></span>

<span data-ttu-id="cad05-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="cad05-115">The type of `array` elements.</span></span>
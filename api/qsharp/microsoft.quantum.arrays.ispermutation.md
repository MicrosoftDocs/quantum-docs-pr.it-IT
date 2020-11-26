---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220927"
---
# <a name="ispermutation-function"></a><span data-ttu-id="59039-102">Funzione Permutation</span><span class="sxs-lookup"><span data-stu-id="59039-102">IsPermutation function</span></span>

<span data-ttu-id="59039-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="59039-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="59039-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59039-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59039-105">Restituisce true se e solo se una determinata matrice rappresenta una permutazione.</span><span class="sxs-lookup"><span data-stu-id="59039-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="59039-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59039-106">Description</span></span>

<span data-ttu-id="59039-107">Data una matrice `array` di lunghezza `n` , restituisce true solo se ogni intero da `0` a `n - 1` viene visualizzato esattamente una volta in `array` , in modo che `array` possa essere interpretato come una permutazione sugli `n` elementi.</span><span class="sxs-lookup"><span data-stu-id="59039-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="59039-108">Input</span><span class="sxs-lookup"><span data-stu-id="59039-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="59039-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="59039-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="59039-110">Matrice che può rappresentare o meno una permutazione.</span><span class="sxs-lookup"><span data-stu-id="59039-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="59039-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59039-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="59039-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="59039-112">Remarks</span></span>

<span data-ttu-id="59039-113">Una matrice di lunghezza zero è una permutazione.</span><span class="sxs-lookup"><span data-stu-id="59039-113">An array of length zero is trivially a permutation.</span></span>
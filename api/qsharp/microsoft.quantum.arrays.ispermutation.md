---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719106"
---
# <a name="ispermutation-function"></a><span data-ttu-id="41f16-102">Funzione Permutation</span><span class="sxs-lookup"><span data-stu-id="41f16-102">IsPermutation function</span></span>

<span data-ttu-id="41f16-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41f16-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41f16-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41f16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41f16-105">Restituisce true se e solo se una determinata matrice rappresenta una permutazione.</span><span class="sxs-lookup"><span data-stu-id="41f16-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="41f16-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41f16-106">Description</span></span>

<span data-ttu-id="41f16-107">Data una matrice `array` di lunghezza `n` , restituisce true solo se ogni intero da `0` a `n - 1` viene visualizzato esattamente una volta in `array` , in modo che `array` possa essere interpretato come una permutazione sugli `n` elementi.</span><span class="sxs-lookup"><span data-stu-id="41f16-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="41f16-108">Input</span><span class="sxs-lookup"><span data-stu-id="41f16-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="41f16-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="41f16-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="41f16-110">Matrice che può rappresentare o meno una permutazione.</span><span class="sxs-lookup"><span data-stu-id="41f16-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="41f16-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41f16-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="41f16-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="41f16-112">Remarks</span></span>

<span data-ttu-id="41f16-113">Una matrice di lunghezza zero è una permutazione.</span><span class="sxs-lookup"><span data-stu-id="41f16-113">An array of length zero is trivially a permutation.</span></span>
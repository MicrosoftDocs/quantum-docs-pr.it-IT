---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848101"
---
# <a name="ispermutation-function"></a><span data-ttu-id="67302-102">Funzione Permutation</span><span class="sxs-lookup"><span data-stu-id="67302-102">IsPermutation function</span></span>

<span data-ttu-id="67302-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="67302-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="67302-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67302-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67302-105">Restituisce true se e solo se una determinata matrice rappresenta una permutazione.</span><span class="sxs-lookup"><span data-stu-id="67302-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="67302-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67302-106">Description</span></span>

<span data-ttu-id="67302-107">Data una matrice `array` di lunghezza `n` , restituisce true solo se ogni intero da `0` a `n - 1` viene visualizzato esattamente una volta in `array` , in modo che `array` possa essere interpretato come una permutazione sugli `n` elementi.</span><span class="sxs-lookup"><span data-stu-id="67302-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="67302-108">Input</span><span class="sxs-lookup"><span data-stu-id="67302-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="67302-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="67302-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="67302-110">Matrice che può rappresentare o meno una permutazione.</span><span class="sxs-lookup"><span data-stu-id="67302-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="67302-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67302-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="67302-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="67302-112">Example</span></span>

<span data-ttu-id="67302-113">Il codice Q # seguente stampa il messaggio "tutti i dati di diagnostica sono stati completati correttamente":</span><span class="sxs-lookup"><span data-stu-id="67302-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="67302-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="67302-114">Remarks</span></span>

<span data-ttu-id="67302-115">Una matrice di lunghezza zero è una permutazione.</span><span class="sxs-lookup"><span data-stu-id="67302-115">An array of length zero is trivially a permutation.</span></span>
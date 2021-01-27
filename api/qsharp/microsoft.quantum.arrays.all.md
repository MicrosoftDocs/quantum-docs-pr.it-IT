---
uid: Microsoft.Quantum.Arrays.All
title: All (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842889"
---
# <a name="all-function"></a><span data-ttu-id="0c2a4-102">All (funzione)</span><span class="sxs-lookup"><span data-stu-id="0c2a4-102">All function</span></span>

<span data-ttu-id="0c2a4-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0c2a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0c2a4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c2a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c2a4-105">Data una matrice e un predicato definito per gli elementi della matrice e controlla se tutti gli elementi della matrice soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="0c2a4-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="0c2a4-106">Input</span><span class="sxs-lookup"><span data-stu-id="0c2a4-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="0c2a4-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0c2a4-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c2a4-108">Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0c2a4-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="0c2a4-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="0c2a4-109">array : 'T[]</span></span>

<span data-ttu-id="0c2a4-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="0c2a4-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0c2a4-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0c2a4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c2a4-112">`Bool`Valore della funzione e del predicato applicato a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0c2a4-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0c2a4-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0c2a4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c2a4-114">T</span><span class="sxs-lookup"><span data-stu-id="0c2a4-114">'T</span></span>

<span data-ttu-id="0c2a4-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="0c2a4-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="0c2a4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c2a4-116">Example</span></span>

<span data-ttu-id="0c2a4-117">Il codice seguente controlla se tutti gli elementi della matrice sono diversi da zero:</span><span class="sxs-lookup"><span data-stu-id="0c2a4-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="0c2a4-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="0c2a4-118">Remarks</span></span>

<span data-ttu-id="0c2a4-119">La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se tutti gli elementi soddisfano `predicate` .</span><span class="sxs-lookup"><span data-stu-id="0c2a4-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>
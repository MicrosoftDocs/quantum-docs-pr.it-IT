---
uid: Microsoft.Quantum.Arrays.Chunks
title: Blocchi (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221607"
---
# <a name="chunks-function"></a><span data-ttu-id="19304-102">Blocchi (funzione)</span><span class="sxs-lookup"><span data-stu-id="19304-102">Chunks function</span></span>

<span data-ttu-id="19304-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="19304-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="19304-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19304-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19304-105">Suddivide una matrice in più parti di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="19304-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="19304-106">Input</span><span class="sxs-lookup"><span data-stu-id="19304-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="19304-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19304-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19304-108">Lunghezza di ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="19304-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="19304-109">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="19304-109">arr : 'T[]</span></span>

<span data-ttu-id="19304-110">Matrice da suddividere.</span><span class="sxs-lookup"><span data-stu-id="19304-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="19304-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="19304-111">Output : 'T[][]</span></span>

<span data-ttu-id="19304-112">Matrice contenente ogni blocco della matrice originale.</span><span class="sxs-lookup"><span data-stu-id="19304-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="19304-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="19304-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19304-114">T</span><span class="sxs-lookup"><span data-stu-id="19304-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="19304-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="19304-115">Remarks</span></span>

<span data-ttu-id="19304-116">Si noti che l'ultimo elemento dell'output può essere minore di `nElements` se `Length(arr)` non è divisibile da `nElements` .</span><span class="sxs-lookup"><span data-stu-id="19304-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>
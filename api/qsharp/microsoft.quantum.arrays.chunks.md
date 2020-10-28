---
uid: Microsoft.Quantum.Arrays.Chunks
title: Blocchi (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719466"
---
# <a name="chunks-function"></a><span data-ttu-id="95f79-102">Blocchi (funzione)</span><span class="sxs-lookup"><span data-stu-id="95f79-102">Chunks function</span></span>

<span data-ttu-id="95f79-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95f79-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95f79-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95f79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95f79-105">Suddivide una matrice in più parti di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="95f79-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="95f79-106">Input</span><span class="sxs-lookup"><span data-stu-id="95f79-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="95f79-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95f79-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95f79-108">Lunghezza di ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="95f79-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="95f79-109">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="95f79-109">arr : 'T[]</span></span>

<span data-ttu-id="95f79-110">Matrice da suddividere.</span><span class="sxs-lookup"><span data-stu-id="95f79-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="95f79-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="95f79-111">Output : 'T[][]</span></span>

<span data-ttu-id="95f79-112">Matrice contenente ogni blocco della matrice originale.</span><span class="sxs-lookup"><span data-stu-id="95f79-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95f79-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="95f79-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95f79-114">T</span><span class="sxs-lookup"><span data-stu-id="95f79-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="95f79-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="95f79-115">Remarks</span></span>

<span data-ttu-id="95f79-116">Si noti che l'ultimo elemento dell'output può essere minore di `nElements` se `Length(arr)` non è divisibile da `nElements` .</span><span class="sxs-lookup"><span data-stu-id="95f79-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>
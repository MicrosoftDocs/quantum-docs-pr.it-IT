---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Funzione partizionata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718974"
---
# <a name="partitioned-function"></a><span data-ttu-id="a0071-102">Funzione partizionata</span><span class="sxs-lookup"><span data-stu-id="a0071-102">Partitioned function</span></span>

<span data-ttu-id="a0071-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0071-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0071-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0071-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0071-105">Suddivide una matrice in più parti.</span><span class="sxs-lookup"><span data-stu-id="a0071-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a0071-106">Input</span><span class="sxs-lookup"><span data-stu-id="a0071-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="a0071-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a0071-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a0071-108">Numero di elementi in ogni parte della matrice</span><span class="sxs-lookup"><span data-stu-id="a0071-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="a0071-109">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="a0071-109">arr : 'T[]</span></span>

<span data-ttu-id="a0071-110">Matrice di input da suddividere.</span><span class="sxs-lookup"><span data-stu-id="a0071-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="a0071-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="a0071-111">Output : 'T[][]</span></span>

<span data-ttu-id="a0071-112">Più matrici in cui la prima matrice è la prima `nElements[0]` di `arr` e la seconda matrice è la successiva `nElements[1]` di e `arr` così via. L'ultima matrice conterrà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a0071-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0071-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a0071-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0071-114">T</span><span class="sxs-lookup"><span data-stu-id="a0071-114">'T</span></span>


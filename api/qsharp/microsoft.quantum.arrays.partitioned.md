---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Funzione partizionata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220502"
---
# <a name="partitioned-function"></a><span data-ttu-id="60a6a-102">Funzione partizionata</span><span class="sxs-lookup"><span data-stu-id="60a6a-102">Partitioned function</span></span>

<span data-ttu-id="60a6a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60a6a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60a6a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60a6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60a6a-105">Suddivide una matrice in più parti.</span><span class="sxs-lookup"><span data-stu-id="60a6a-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="60a6a-106">Input</span><span class="sxs-lookup"><span data-stu-id="60a6a-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="60a6a-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="60a6a-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="60a6a-108">Numero di elementi in ogni parte della matrice</span><span class="sxs-lookup"><span data-stu-id="60a6a-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="60a6a-109">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="60a6a-109">arr : 'T[]</span></span>

<span data-ttu-id="60a6a-110">Matrice di input da suddividere.</span><span class="sxs-lookup"><span data-stu-id="60a6a-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="60a6a-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="60a6a-111">Output : 'T[][]</span></span>

<span data-ttu-id="60a6a-112">Più matrici in cui la prima matrice è la prima `nElements[0]` di `arr` e la seconda matrice è la successiva `nElements[1]` di e `arr` così via. L'ultima matrice conterrà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="60a6a-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60a6a-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="60a6a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60a6a-114">T</span><span class="sxs-lookup"><span data-stu-id="60a6a-114">'T</span></span>


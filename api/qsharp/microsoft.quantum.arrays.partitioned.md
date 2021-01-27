---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Funzione partizionata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845551"
---
# <a name="partitioned-function"></a><span data-ttu-id="a0f36-102">Funzione partizionata</span><span class="sxs-lookup"><span data-stu-id="a0f36-102">Partitioned function</span></span>

<span data-ttu-id="a0f36-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0f36-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0f36-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0f36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0f36-105">Suddivide una matrice in più parti.</span><span class="sxs-lookup"><span data-stu-id="a0f36-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a0f36-106">Input</span><span class="sxs-lookup"><span data-stu-id="a0f36-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="a0f36-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a0f36-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a0f36-108">Numero di elementi in ogni parte della matrice</span><span class="sxs-lookup"><span data-stu-id="a0f36-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="a0f36-109">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="a0f36-109">arr : 'T[]</span></span>

<span data-ttu-id="a0f36-110">Matrice di input da suddividere.</span><span class="sxs-lookup"><span data-stu-id="a0f36-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="a0f36-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="a0f36-111">Output : 'T[][]</span></span>

<span data-ttu-id="a0f36-112">Più matrici in cui la prima matrice è la prima `nElements[0]` di `arr` e la seconda matrice è la successiva `nElements[1]` di e `arr` così via. L'ultima matrice conterrà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a0f36-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0f36-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a0f36-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0f36-114">T</span><span class="sxs-lookup"><span data-stu-id="a0f36-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="a0f36-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0f36-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```
---
uid: Microsoft.Quantum.Arrays.Swapped
title: Funzione scambiata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220128"
---
# <a name="swapped-function"></a><span data-ttu-id="8b53f-102">Funzione scambiata</span><span class="sxs-lookup"><span data-stu-id="8b53f-102">Swapped function</span></span>

<span data-ttu-id="8b53f-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b53f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b53f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b53f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b53f-105">Applica uno scambio di due elementi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="8b53f-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8b53f-106">Input</span><span class="sxs-lookup"><span data-stu-id="8b53f-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="8b53f-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b53f-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b53f-108">Indice del primo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="8b53f-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="8b53f-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b53f-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b53f-110">Indice del secondo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="8b53f-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="8b53f-111">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="8b53f-111">arr : 'T[]</span></span>

<span data-ttu-id="8b53f-112">Matrice con elementi da scambiare.</span><span class="sxs-lookup"><span data-stu-id="8b53f-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="8b53f-113">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="8b53f-113">Output : 'T[]</span></span>

<span data-ttu-id="8b53f-114">Matrice con lo swap sul posto applicato.</span><span class="sxs-lookup"><span data-stu-id="8b53f-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="8b53f-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b53f-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="8b53f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8b53f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b53f-117">T</span><span class="sxs-lookup"><span data-stu-id="8b53f-117">'T</span></span>


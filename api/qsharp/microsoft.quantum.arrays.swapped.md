---
uid: Microsoft.Quantum.Arrays.Swapped
title: Funzione scambiata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850944"
---
# <a name="swapped-function"></a><span data-ttu-id="e8871-102">Funzione scambiata</span><span class="sxs-lookup"><span data-stu-id="e8871-102">Swapped function</span></span>

<span data-ttu-id="e8871-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8871-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8871-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8871-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8871-105">Applica uno scambio di due elementi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="e8871-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8871-106">Input</span><span class="sxs-lookup"><span data-stu-id="e8871-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="e8871-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8871-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8871-108">Indice del primo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="e8871-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="e8871-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8871-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8871-110">Indice del secondo elemento da scambiare.</span><span class="sxs-lookup"><span data-stu-id="e8871-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e8871-111">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="e8871-111">arr : 'T[]</span></span>

<span data-ttu-id="e8871-112">Matrice con elementi da scambiare.</span><span class="sxs-lookup"><span data-stu-id="e8871-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="e8871-113">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="e8871-113">Output : 'T[]</span></span>

<span data-ttu-id="e8871-114">Matrice con lo swap sul posto applicato.</span><span class="sxs-lookup"><span data-stu-id="e8871-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="e8871-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8871-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="e8871-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e8871-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8871-117">T</span><span class="sxs-lookup"><span data-stu-id="e8871-117">'T</span></span>


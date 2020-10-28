---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: edd05dcf2e7560d777d8031f45b7e444bb1935b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719367"
---
# <a name="elementat-function"></a><span data-ttu-id="e98c2-102">ElementAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="e98c2-102">ElementAt function</span></span>

<span data-ttu-id="e98c2-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e98c2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e98c2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e98c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e98c2-105">Restituisce l'oggetto in corrispondenza dell'indice specificato di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e98c2-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="e98c2-106">Input</span><span class="sxs-lookup"><span data-stu-id="e98c2-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="e98c2-107">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e98c2-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e98c2-108">Index dell'elemento</span><span class="sxs-lookup"><span data-stu-id="e98c2-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="e98c2-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="e98c2-109">array : 'T[]</span></span>

<span data-ttu-id="e98c2-110">Matrice da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="e98c2-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="e98c2-111">Output:' t</span><span class="sxs-lookup"><span data-stu-id="e98c2-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e98c2-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e98c2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e98c2-113">T</span><span class="sxs-lookup"><span data-stu-id="e98c2-113">'T</span></span>

<span data-ttu-id="e98c2-114">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="e98c2-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e98c2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e98c2-115">See Also</span></span>

- [<span data-ttu-id="e98c2-116">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="e98c2-116">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="e98c2-117">Microsoft. Quantum. Arrays. ElementsAt</span><span class="sxs-lookup"><span data-stu-id="e98c2-117">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)
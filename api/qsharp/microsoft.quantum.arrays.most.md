---
uid: Microsoft.Quantum.Arrays.Most
title: Funzione most
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718998"
---
# <a name="most-function"></a><span data-ttu-id="c01f4-102">Funzione most</span><span class="sxs-lookup"><span data-stu-id="c01f4-102">Most function</span></span>

<span data-ttu-id="c01f4-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c01f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c01f4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c01f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c01f4-105">Crea una matrice uguale a una matrice di input, ad eccezione del fatto che l'ultimo elemento della matrice viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="c01f4-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c01f4-106">Input</span><span class="sxs-lookup"><span data-stu-id="c01f4-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c01f4-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="c01f4-107">array : 'T[]</span></span>

<span data-ttu-id="c01f4-108">Matrice il cui primo è costituito da un penultimo elemento per formare la matrice di output.</span><span class="sxs-lookup"><span data-stu-id="c01f4-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="c01f4-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="c01f4-109">Output : 'T[]</span></span>

<span data-ttu-id="c01f4-110">Matrice contenente gli elementi `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="c01f4-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c01f4-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c01f4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c01f4-112">T</span><span class="sxs-lookup"><span data-stu-id="c01f4-112">'T</span></span>

<span data-ttu-id="c01f4-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="c01f4-113">The type of the array elements.</span></span>
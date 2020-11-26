---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220393"
---
# <a name="rest-function"></a><span data-ttu-id="d0e7f-102">Rest (funzione)</span><span class="sxs-lookup"><span data-stu-id="d0e7f-102">Rest function</span></span>

<span data-ttu-id="d0e7f-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0e7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0e7f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0e7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0e7f-105">Crea una matrice uguale a una matrice di input, ad eccezione del fatto che il primo elemento della matrice viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d0e7f-106">Input</span><span class="sxs-lookup"><span data-stu-id="d0e7f-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d0e7f-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="d0e7f-107">array : 'T[]</span></span>

<span data-ttu-id="d0e7f-108">Matrice il cui penultimo elemento consiste nel formare la matrice di output.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0e7f-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="d0e7f-109">Output : 'T[]</span></span>

<span data-ttu-id="d0e7f-110">Matrice contenente gli elementi `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="d0e7f-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0e7f-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d0e7f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0e7f-112">T</span><span class="sxs-lookup"><span data-stu-id="d0e7f-112">'T</span></span>

<span data-ttu-id="d0e7f-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-113">The type of the array elements.</span></span>
---
uid: Microsoft.Quantum.Arrays.Most
title: Funzione most
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845572"
---
# <a name="most-function"></a><span data-ttu-id="35813-102">Funzione most</span><span class="sxs-lookup"><span data-stu-id="35813-102">Most function</span></span>

<span data-ttu-id="35813-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35813-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35813-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35813-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35813-105">Crea una matrice uguale a una matrice di input, ad eccezione del fatto che l'ultimo elemento della matrice viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="35813-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="35813-106">Input</span><span class="sxs-lookup"><span data-stu-id="35813-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="35813-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="35813-107">array : 'T[]</span></span>

<span data-ttu-id="35813-108">Matrice il cui primo è costituito da un penultimo elemento per formare la matrice di output.</span><span class="sxs-lookup"><span data-stu-id="35813-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="35813-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="35813-109">Output : 'T[]</span></span>

<span data-ttu-id="35813-110">Matrice contenente gli elementi `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="35813-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35813-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="35813-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35813-112">T</span><span class="sxs-lookup"><span data-stu-id="35813-112">'T</span></span>

<span data-ttu-id="35813-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="35813-113">The type of the array elements.</span></span>
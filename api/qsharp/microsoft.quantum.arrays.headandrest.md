---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719178"
---
# <a name="headandrest-function"></a><span data-ttu-id="012b9-102">HeadAndRest (funzione)</span><span class="sxs-lookup"><span data-stu-id="012b9-102">HeadAndRest function</span></span>

<span data-ttu-id="012b9-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="012b9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="012b9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="012b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="012b9-105">Restituisce una tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="012b9-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="012b9-106">Input</span><span class="sxs-lookup"><span data-stu-id="012b9-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="012b9-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="012b9-107">array : 'A[]</span></span>

<span data-ttu-id="012b9-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="012b9-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="012b9-109">Output: (' A,' A [])</span><span class="sxs-lookup"><span data-stu-id="012b9-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="012b9-110">Tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="012b9-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="012b9-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="012b9-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="012b9-112">' A</span><span class="sxs-lookup"><span data-stu-id="012b9-112">'A</span></span>

<span data-ttu-id="012b9-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="012b9-113">The type of the array elements.</span></span>
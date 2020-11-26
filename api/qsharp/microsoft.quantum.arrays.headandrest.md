---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221080"
---
# <a name="headandrest-function"></a><span data-ttu-id="c52ba-102">HeadAndRest (funzione)</span><span class="sxs-lookup"><span data-stu-id="c52ba-102">HeadAndRest function</span></span>

<span data-ttu-id="c52ba-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c52ba-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c52ba-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c52ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c52ba-105">Restituisce una tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="c52ba-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="c52ba-106">Input</span><span class="sxs-lookup"><span data-stu-id="c52ba-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="c52ba-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="c52ba-107">array : 'A[]</span></span>

<span data-ttu-id="c52ba-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="c52ba-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="c52ba-109">Output: (' A,' A [])</span><span class="sxs-lookup"><span data-stu-id="c52ba-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="c52ba-110">Tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="c52ba-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c52ba-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c52ba-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="c52ba-112">' A</span><span class="sxs-lookup"><span data-stu-id="c52ba-112">'A</span></span>

<span data-ttu-id="c52ba-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="c52ba-113">The type of the array elements.</span></span>
---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845597"
---
# <a name="mostandtail-function"></a><span data-ttu-id="d3ec8-102">MostAndTail (funzione)</span><span class="sxs-lookup"><span data-stu-id="d3ec8-102">MostAndTail function</span></span>

<span data-ttu-id="d3ec8-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d3ec8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d3ec8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3ec8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3ec8-105">Restituisce una tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="d3ec8-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="d3ec8-106">Input</span><span class="sxs-lookup"><span data-stu-id="d3ec8-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="d3ec8-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="d3ec8-107">array : 'A[]</span></span>

<span data-ttu-id="d3ec8-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="d3ec8-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="d3ec8-109">Output: (' A [],' A)</span><span class="sxs-lookup"><span data-stu-id="d3ec8-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="d3ec8-110">Tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="d3ec8-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d3ec8-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d3ec8-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="d3ec8-112">' A</span><span class="sxs-lookup"><span data-stu-id="d3ec8-112">'A</span></span>

<span data-ttu-id="d3ec8-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="d3ec8-113">The type of the array elements.</span></span>
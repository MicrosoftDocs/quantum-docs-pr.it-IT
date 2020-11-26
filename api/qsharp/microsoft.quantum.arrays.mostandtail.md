---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220570"
---
# <a name="mostandtail-function"></a><span data-ttu-id="3e2a0-102">MostAndTail (funzione)</span><span class="sxs-lookup"><span data-stu-id="3e2a0-102">MostAndTail function</span></span>

<span data-ttu-id="3e2a0-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3e2a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3e2a0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e2a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e2a0-105">Restituisce una tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="3e2a0-106">Input</span><span class="sxs-lookup"><span data-stu-id="3e2a0-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="3e2a0-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="3e2a0-107">array : 'A[]</span></span>

<span data-ttu-id="3e2a0-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="3e2a0-109">Output: (' A [],' A)</span><span class="sxs-lookup"><span data-stu-id="3e2a0-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="3e2a0-110">Tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3e2a0-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3e2a0-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="3e2a0-112">' A</span><span class="sxs-lookup"><span data-stu-id="3e2a0-112">'A</span></span>

<span data-ttu-id="3e2a0-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-113">The type of the array elements.</span></span>
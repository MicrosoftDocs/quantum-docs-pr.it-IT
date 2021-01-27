---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848555"
---
# <a name="headandrest-function"></a><span data-ttu-id="f738a-102">HeadAndRest (funzione)</span><span class="sxs-lookup"><span data-stu-id="f738a-102">HeadAndRest function</span></span>

<span data-ttu-id="f738a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f738a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f738a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f738a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f738a-105">Restituisce una tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="f738a-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="f738a-106">Input</span><span class="sxs-lookup"><span data-stu-id="f738a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="f738a-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="f738a-107">array : 'A[]</span></span>

<span data-ttu-id="f738a-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="f738a-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="f738a-109">Output: (' A,' A [])</span><span class="sxs-lookup"><span data-stu-id="f738a-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="f738a-110">Tupla del primo e di tutti gli elementi rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="f738a-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f738a-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f738a-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="f738a-112">' A</span><span class="sxs-lookup"><span data-stu-id="f738a-112">'A</span></span>

<span data-ttu-id="f738a-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f738a-113">The type of the array elements.</span></span>
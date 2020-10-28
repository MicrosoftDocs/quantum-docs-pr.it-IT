---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718995"
---
# <a name="mostandtail-function"></a><span data-ttu-id="8bd83-102">MostAndTail (funzione)</span><span class="sxs-lookup"><span data-stu-id="8bd83-102">MostAndTail function</span></span>

<span data-ttu-id="8bd83-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8bd83-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8bd83-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bd83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bd83-105">Restituisce una tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="8bd83-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="8bd83-106">Input</span><span class="sxs-lookup"><span data-stu-id="8bd83-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="8bd83-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="8bd83-107">array : 'A[]</span></span>

<span data-ttu-id="8bd83-108">Matrice con almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="8bd83-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="8bd83-109">Output: (' A [],' A)</span><span class="sxs-lookup"><span data-stu-id="8bd83-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="8bd83-110">Tupla di tutti gli elementi tranne uno e l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="8bd83-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8bd83-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8bd83-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="8bd83-112">' A</span><span class="sxs-lookup"><span data-stu-id="8bd83-112">'A</span></span>

<span data-ttu-id="8bd83-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8bd83-113">The type of the array elements.</span></span>
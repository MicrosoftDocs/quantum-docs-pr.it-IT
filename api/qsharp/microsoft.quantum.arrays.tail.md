---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail - funzione
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220094"
---
# <a name="tail-function"></a><span data-ttu-id="45c30-102">Tail - funzione</span><span class="sxs-lookup"><span data-stu-id="45c30-102">Tail function</span></span>

<span data-ttu-id="45c30-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45c30-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45c30-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45c30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45c30-105">Restituisce l'ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="45c30-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="45c30-106">Input</span><span class="sxs-lookup"><span data-stu-id="45c30-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="45c30-107">array:' A []</span><span class="sxs-lookup"><span data-stu-id="45c30-107">array : 'A[]</span></span>

<span data-ttu-id="45c30-108">Matrice di cui viene utilizzato l'ultimo elemento.</span><span class="sxs-lookup"><span data-stu-id="45c30-108">Array of which the last element is taken.</span></span> <span data-ttu-id="45c30-109">La matrice deve avere una lunghezza almeno pari a 1.</span><span class="sxs-lookup"><span data-stu-id="45c30-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="45c30-110">Output:' A</span><span class="sxs-lookup"><span data-stu-id="45c30-110">Output : 'A</span></span>

<span data-ttu-id="45c30-111">Ultimo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="45c30-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45c30-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="45c30-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="45c30-113">' A</span><span class="sxs-lookup"><span data-stu-id="45c30-113">'A</span></span>

<span data-ttu-id="45c30-114">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="45c30-114">The type of the array elements.</span></span>
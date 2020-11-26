---
uid: Microsoft.Quantum.Arrays.Reversed
title: Funzione invertita
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220434"
---
# <a name="reversed-function"></a><span data-ttu-id="0041d-102">Funzione invertita</span><span class="sxs-lookup"><span data-stu-id="0041d-102">Reversed function</span></span>

<span data-ttu-id="0041d-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0041d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0041d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0041d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0041d-105">Creare una matrice che contiene gli stessi elementi di una matrice di input, ma in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="0041d-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0041d-106">Input</span><span class="sxs-lookup"><span data-stu-id="0041d-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="0041d-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="0041d-107">array : 'T[]</span></span>

<span data-ttu-id="0041d-108">Matrice i cui elementi devono essere copiati in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="0041d-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="0041d-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="0041d-109">Output : 'T[]</span></span>

<span data-ttu-id="0041d-110">Matrice contenente gli elementi `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="0041d-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="0041d-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="0041d-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0041d-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0041d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0041d-113">T</span><span class="sxs-lookup"><span data-stu-id="0041d-113">'T</span></span>

<span data-ttu-id="0041d-114">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="0041d-114">The type of the array elements.</span></span>
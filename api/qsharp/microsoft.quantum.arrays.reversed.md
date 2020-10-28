---
uid: Microsoft.Quantum.Arrays.Reversed
title: Funzione invertita
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718911"
---
# <a name="reversed-function"></a><span data-ttu-id="bc9b8-102">Funzione invertita</span><span class="sxs-lookup"><span data-stu-id="bc9b8-102">Reversed function</span></span>

<span data-ttu-id="bc9b8-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc9b8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc9b8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc9b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc9b8-105">Creare una matrice che contiene gli stessi elementi di una matrice di input, ma in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bc9b8-106">Input</span><span class="sxs-lookup"><span data-stu-id="bc9b8-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bc9b8-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="bc9b8-107">array : 'T[]</span></span>

<span data-ttu-id="bc9b8-108">Matrice i cui elementi devono essere copiati in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="bc9b8-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="bc9b8-109">Output : 'T[]</span></span>

<span data-ttu-id="bc9b8-110">Matrice contenente gli elementi `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="bc9b8-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="bc9b8-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bc9b8-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bc9b8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc9b8-113">T</span><span class="sxs-lookup"><span data-stu-id="bc9b8-113">'T</span></span>

<span data-ttu-id="bc9b8-114">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-114">The type of the array elements.</span></span>
---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718914"
---
# <a name="rest-function"></a><span data-ttu-id="b8219-102">Rest (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8219-102">Rest function</span></span>

<span data-ttu-id="b8219-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b8219-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b8219-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8219-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8219-105">Crea una matrice uguale a una matrice di input, ad eccezione del fatto che il primo elemento della matrice viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="b8219-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b8219-106">Input</span><span class="sxs-lookup"><span data-stu-id="b8219-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b8219-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="b8219-107">array : 'T[]</span></span>

<span data-ttu-id="b8219-108">Matrice il cui penultimo elemento consiste nel formare la matrice di output.</span><span class="sxs-lookup"><span data-stu-id="b8219-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b8219-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="b8219-109">Output : 'T[]</span></span>

<span data-ttu-id="b8219-110">Matrice contenente gli elementi `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b8219-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b8219-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b8219-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8219-112">T</span><span class="sxs-lookup"><span data-stu-id="b8219-112">'T</span></span>

<span data-ttu-id="b8219-113">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="b8219-113">The type of the array elements.</span></span>
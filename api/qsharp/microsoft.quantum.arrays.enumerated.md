---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funzione enumerata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719307"
---
# <a name="enumerated-function"></a><span data-ttu-id="b59a2-102">Funzione enumerata</span><span class="sxs-lookup"><span data-stu-id="b59a2-102">Enumerated function</span></span>

<span data-ttu-id="b59a2-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b59a2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b59a2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b59a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b59a2-105">Data una matrice, restituisce una nuova matrice contenente gli elementi della matrice originale insieme agli indici di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="b59a2-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="b59a2-106">Input</span><span class="sxs-lookup"><span data-stu-id="b59a2-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="b59a2-107">matrice:' TElement []</span><span class="sxs-lookup"><span data-stu-id="b59a2-107">array : 'TElement[]</span></span>

<span data-ttu-id="b59a2-108">Matrice i cui elementi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="b59a2-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="b59a2-109">Output: ([int](xref:microsoft.quantum.lang-ref.int),' TElement) []</span><span class="sxs-lookup"><span data-stu-id="b59a2-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="b59a2-110">Nuova matrice contenente gli elementi della matrice originale insieme ai relativi indici.</span><span class="sxs-lookup"><span data-stu-id="b59a2-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b59a2-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b59a2-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="b59a2-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="b59a2-112">'TElement</span></span>

<span data-ttu-id="b59a2-113">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="b59a2-113">The type of elements of the array.</span></span>
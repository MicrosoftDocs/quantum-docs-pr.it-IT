---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220961"
---
# <a name="interleaved-function"></a><span data-ttu-id="60ea2-102">Funzione Interleaved</span><span class="sxs-lookup"><span data-stu-id="60ea2-102">Interleaved function</span></span>

<span data-ttu-id="60ea2-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60ea2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60ea2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60ea2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60ea2-105">Interleaves due matrici di (quasi) stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="60ea2-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="60ea2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ea2-106">Description</span></span>

<span data-ttu-id="60ea2-107">Questa funzione restituisce l'interfoliazione di due matrici, a partire dal primo elemento della prima matrice, dal primo elemento della seconda matrice e così via.</span><span class="sxs-lookup"><span data-stu-id="60ea2-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="60ea2-108">La prima matrice deve avere la stessa lunghezza del secondo oppure può avere un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="60ea2-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="60ea2-109">Input</span><span class="sxs-lookup"><span data-stu-id="60ea2-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="60ea2-110">primo:' t []</span><span class="sxs-lookup"><span data-stu-id="60ea2-110">first : 'T[]</span></span>

<span data-ttu-id="60ea2-111">Prima matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="60ea2-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="60ea2-112">secondo:' t []</span><span class="sxs-lookup"><span data-stu-id="60ea2-112">second : 'T[]</span></span>

<span data-ttu-id="60ea2-113">Seconda matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="60ea2-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="60ea2-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="60ea2-114">Output : 'T[]</span></span>

<span data-ttu-id="60ea2-115">Matrice Interleaved</span><span class="sxs-lookup"><span data-stu-id="60ea2-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60ea2-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="60ea2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60ea2-117">T</span><span class="sxs-lookup"><span data-stu-id="60ea2-117">'T</span></span>

<span data-ttu-id="60ea2-118">Tipo di ogni elemento di `first` e `second` .</span><span class="sxs-lookup"><span data-stu-id="60ea2-118">The type of each element of `first` and `second`.</span></span>
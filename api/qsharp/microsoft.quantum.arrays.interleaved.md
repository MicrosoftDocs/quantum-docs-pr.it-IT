---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719142"
---
# <a name="interleaved-function"></a><span data-ttu-id="0c205-102">Funzione Interleaved</span><span class="sxs-lookup"><span data-stu-id="0c205-102">Interleaved function</span></span>

<span data-ttu-id="0c205-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0c205-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0c205-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c205-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c205-105">Interleaves due matrici di (quasi) stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0c205-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="0c205-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c205-106">Description</span></span>

<span data-ttu-id="0c205-107">Questa funzione restituisce l'interfoliazione di due matrici, a partire dal primo elemento della prima matrice, dal primo elemento della seconda matrice e così via.</span><span class="sxs-lookup"><span data-stu-id="0c205-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="0c205-108">La prima matrice deve avere la stessa lunghezza del secondo oppure può avere un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0c205-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="0c205-109">Input</span><span class="sxs-lookup"><span data-stu-id="0c205-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="0c205-110">primo:' t []</span><span class="sxs-lookup"><span data-stu-id="0c205-110">first : 'T[]</span></span>

<span data-ttu-id="0c205-111">Prima matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="0c205-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="0c205-112">secondo:' t []</span><span class="sxs-lookup"><span data-stu-id="0c205-112">second : 'T[]</span></span>

<span data-ttu-id="0c205-113">Seconda matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="0c205-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="0c205-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="0c205-114">Output : 'T[]</span></span>

<span data-ttu-id="0c205-115">Matrice Interleaved</span><span class="sxs-lookup"><span data-stu-id="0c205-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0c205-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0c205-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c205-117">T</span><span class="sxs-lookup"><span data-stu-id="0c205-117">'T</span></span>

<span data-ttu-id="0c205-118">Tipo di ogni elemento di `first` e `second` .</span><span class="sxs-lookup"><span data-stu-id="0c205-118">The type of each element of `first` and `second`.</span></span>
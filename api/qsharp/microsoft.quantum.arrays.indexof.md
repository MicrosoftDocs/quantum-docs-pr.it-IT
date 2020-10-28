---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funzione IndexOf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719175"
---
# <a name="indexof-function"></a><span data-ttu-id="9b2dd-102">Funzione IndexOf</span><span class="sxs-lookup"><span data-stu-id="9b2dd-102">IndexOf function</span></span>

<span data-ttu-id="9b2dd-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9b2dd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9b2dd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b2dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b2dd-105">Restituisce il primo indice del primo elemento di una matrice che soddisfa un predicato specificato.</span><span class="sxs-lookup"><span data-stu-id="9b2dd-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="9b2dd-106">Se tale elemento non esiste, restituisce-1.</span><span class="sxs-lookup"><span data-stu-id="9b2dd-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="9b2dd-107">Input</span><span class="sxs-lookup"><span data-stu-id="9b2dd-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="9b2dd-108">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9b2dd-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9b2dd-109">Funzione di predicato che agisce sugli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="9b2dd-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="9b2dd-110">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="9b2dd-110">arr : 'T[]</span></span>

<span data-ttu-id="9b2dd-111">Matrice da cercare utilizzando il predicato specificato.</span><span class="sxs-lookup"><span data-stu-id="9b2dd-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="9b2dd-112">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b2dd-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b2dd-113">Indice più piccolo in `idx` modo che `predicate(arr[idx])` sia true oppure-1 se tale elemento non esiste.</span><span class="sxs-lookup"><span data-stu-id="9b2dd-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9b2dd-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9b2dd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b2dd-115">T</span><span class="sxs-lookup"><span data-stu-id="9b2dd-115">'T</span></span>


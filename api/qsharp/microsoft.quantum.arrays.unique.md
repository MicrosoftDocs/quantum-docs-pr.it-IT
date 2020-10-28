---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718782"
---
# <a name="unique-function"></a><span data-ttu-id="42de7-102">Unique (funzione)</span><span class="sxs-lookup"><span data-stu-id="42de7-102">Unique function</span></span>

<span data-ttu-id="42de7-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="42de7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="42de7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42de7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42de7-105">Restituisce una nuova matrice che non dispone di elementi adiacenti uguali.</span><span class="sxs-lookup"><span data-stu-id="42de7-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="42de7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42de7-106">Description</span></span>

<span data-ttu-id="42de7-107">Data una matrice di elementi e una funzione per verificare l'uguaglianza, questa funzione restituisce una nuova matrice in cui viene mantenuto l'ordine relativo degli elementi, ma tutti gli elementi adiacenti uguali vengono filtrati in un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="42de7-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="42de7-108">Input</span><span class="sxs-lookup"><span data-stu-id="42de7-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="42de7-109">uguale a: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42de7-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42de7-110">Funzione che confronta due elementi, che `a` sono considerati uguali a `b` se `equal(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="42de7-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="42de7-111">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="42de7-111">array : 'T[]</span></span>

<span data-ttu-id="42de7-112">Matrice da filtrare per gli elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="42de7-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="42de7-113">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="42de7-113">Output : 'T[]</span></span>

<span data-ttu-id="42de7-114">Matrice senza elementi adiacenti uguali.</span><span class="sxs-lookup"><span data-stu-id="42de7-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="42de7-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="42de7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42de7-116">T</span><span class="sxs-lookup"><span data-stu-id="42de7-116">'T</span></span>

<span data-ttu-id="42de7-117">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="42de7-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="42de7-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="42de7-118">Remarks</span></span>

<span data-ttu-id="42de7-119">Se sono presenti più elementi uguali ma non vicini tra loro, saranno presenti più occorrenze nella matrice di output.</span><span class="sxs-lookup"><span data-stu-id="42de7-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="42de7-120">Usare questa funzione insieme `Sorted` a per ottenere una matrice con elementi univoci complessivi.</span><span class="sxs-lookup"><span data-stu-id="42de7-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>
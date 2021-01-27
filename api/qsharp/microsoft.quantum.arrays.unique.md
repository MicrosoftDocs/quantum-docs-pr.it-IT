---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850916"
---
# <a name="unique-function"></a><span data-ttu-id="7ca78-102">Unique (funzione)</span><span class="sxs-lookup"><span data-stu-id="7ca78-102">Unique function</span></span>

<span data-ttu-id="7ca78-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7ca78-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7ca78-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ca78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ca78-105">Restituisce una nuova matrice che non dispone di elementi adiacenti uguali.</span><span class="sxs-lookup"><span data-stu-id="7ca78-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="7ca78-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ca78-106">Description</span></span>

<span data-ttu-id="7ca78-107">Data una matrice di elementi e una funzione per verificare l'uguaglianza, questa funzione restituisce una nuova matrice in cui viene mantenuto l'ordine relativo degli elementi, ma tutti gli elementi adiacenti uguali vengono filtrati in un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="7ca78-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="7ca78-108">Input</span><span class="sxs-lookup"><span data-stu-id="7ca78-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="7ca78-109">uguale a: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7ca78-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7ca78-110">Funzione che confronta due elementi, che `a` sono considerati uguali a `b` se `equal(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="7ca78-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="7ca78-111">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="7ca78-111">array : 'T[]</span></span>

<span data-ttu-id="7ca78-112">Matrice da filtrare per gli elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="7ca78-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="7ca78-113">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="7ca78-113">Output : 'T[]</span></span>

<span data-ttu-id="7ca78-114">Matrice senza elementi adiacenti uguali.</span><span class="sxs-lookup"><span data-stu-id="7ca78-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7ca78-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7ca78-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ca78-116">T</span><span class="sxs-lookup"><span data-stu-id="7ca78-116">'T</span></span>

<span data-ttu-id="7ca78-117">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="7ca78-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="7ca78-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ca78-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="7ca78-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="7ca78-119">Remarks</span></span>

<span data-ttu-id="7ca78-120">Se sono presenti più elementi uguali ma non vicini tra loro, saranno presenti più occorrenze nella matrice di output.</span><span class="sxs-lookup"><span data-stu-id="7ca78-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="7ca78-121">Usare questa funzione insieme `Sorted` a per ottenere una matrice con elementi univoci complessivi.</span><span class="sxs-lookup"><span data-stu-id="7ca78-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>
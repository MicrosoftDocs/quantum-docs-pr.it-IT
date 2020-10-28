---
uid: Microsoft.Quantum.Arrays.Fold
title: Funzione fold
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719211"
---
# <a name="fold-function"></a><span data-ttu-id="afa64-102">Funzione fold</span><span class="sxs-lookup"><span data-stu-id="afa64-102">Fold function</span></span>

<span data-ttu-id="afa64-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afa64-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afa64-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afa64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afa64-105">Scorre una funzione `f` tramite una matrice `array` , restituendo `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="afa64-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="afa64-106">Input</span><span class="sxs-lookup"><span data-stu-id="afa64-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="afa64-107">cartella: (' stato,' non)-stato >'</span><span class="sxs-lookup"><span data-stu-id="afa64-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="afa64-108">Funzione da ripiegare sulla matrice.</span><span class="sxs-lookup"><span data-stu-id="afa64-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="afa64-109">stato:' stato</span><span class="sxs-lookup"><span data-stu-id="afa64-109">state : 'State</span></span>

<span data-ttu-id="afa64-110">Stato iniziale della cartella.</span><span class="sxs-lookup"><span data-stu-id="afa64-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="afa64-111">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="afa64-111">array : 'T[]</span></span>

<span data-ttu-id="afa64-112">Matrice di valori da ripiegare.</span><span class="sxs-lookup"><span data-stu-id="afa64-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="afa64-113">Output:' stato</span><span class="sxs-lookup"><span data-stu-id="afa64-113">Output : 'State</span></span>

<span data-ttu-id="afa64-114">Stato finale restituito dalla cartella dopo l'iterazione su tutti gli elementi di `array` .</span><span class="sxs-lookup"><span data-stu-id="afa64-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afa64-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="afa64-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="afa64-116">' Stato</span><span class="sxs-lookup"><span data-stu-id="afa64-116">'State</span></span>

<span data-ttu-id="afa64-117">Tipo di stati `folder` su cui opera la funzione, ovvero accetta come primo argomento e restituisce.</span><span class="sxs-lookup"><span data-stu-id="afa64-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="afa64-118">T</span><span class="sxs-lookup"><span data-stu-id="afa64-118">'T</span></span>

<span data-ttu-id="afa64-119">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="afa64-119">The type of `array` elements.</span></span>
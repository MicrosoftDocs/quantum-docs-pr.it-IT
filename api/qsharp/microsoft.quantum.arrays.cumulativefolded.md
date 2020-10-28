---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719394"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="b8c67-102">CumulativeFolded (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8c67-102">CumulativeFolded function</span></span>

<span data-ttu-id="b8c67-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b8c67-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b8c67-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8c67-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8c67-105">Combina il mapping e il ripiego in una singola funzione</span><span class="sxs-lookup"><span data-stu-id="b8c67-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="b8c67-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8c67-106">Description</span></span>

<span data-ttu-id="b8c67-107">Questa funzione esegue l'iterazione della `fn` funzione attraverso la matrice, iniziando da uno stato iniziale `state` e restituisce tutti i valori intermedi, escluso lo stato iniziale.</span><span class="sxs-lookup"><span data-stu-id="b8c67-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="b8c67-108">Input</span><span class="sxs-lookup"><span data-stu-id="b8c67-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="b8c67-109">FN: (' state,' t')->' stato</span><span class="sxs-lookup"><span data-stu-id="b8c67-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="b8c67-110">Funzione da ripiegare sulla matrice</span><span class="sxs-lookup"><span data-stu-id="b8c67-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="b8c67-111">stato:' stato</span><span class="sxs-lookup"><span data-stu-id="b8c67-111">state : 'State</span></span>

<span data-ttu-id="b8c67-112">Stato iniziale da ripiegare</span><span class="sxs-lookup"><span data-stu-id="b8c67-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="b8c67-113">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="b8c67-113">array : 'T[]</span></span>

<span data-ttu-id="b8c67-114">Matrice di valori da ripiegare</span><span class="sxs-lookup"><span data-stu-id="b8c67-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="b8c67-115">Output:' stato []</span><span class="sxs-lookup"><span data-stu-id="b8c67-115">Output : 'State[]</span></span>

<span data-ttu-id="b8c67-116">Tutti gli stati intermedi, incluso lo stato finale, ma non lo stato iniziale.</span><span class="sxs-lookup"><span data-stu-id="b8c67-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="b8c67-117">La lunghezza della matrice di output è uguale a quella di `array` .</span><span class="sxs-lookup"><span data-stu-id="b8c67-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b8c67-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b8c67-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="b8c67-119">' Stato</span><span class="sxs-lookup"><span data-stu-id="b8c67-119">'State</span></span>

<span data-ttu-id="b8c67-120">Tipo di stati `fn` su cui opera la funzione, ovvero accetta come primo input e restituisce.</span><span class="sxs-lookup"><span data-stu-id="b8c67-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="b8c67-121">T</span><span class="sxs-lookup"><span data-stu-id="b8c67-121">'T</span></span>

<span data-ttu-id="b8c67-122">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="b8c67-122">The type of `array` elements.</span></span>
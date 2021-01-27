---
uid: Microsoft.Quantum.Arrays.Fold
title: Funzione fold
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848600"
---
# <a name="fold-function"></a><span data-ttu-id="f23ab-102">Funzione fold</span><span class="sxs-lookup"><span data-stu-id="f23ab-102">Fold function</span></span>

<span data-ttu-id="f23ab-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f23ab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f23ab-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f23ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f23ab-105">Scorre una funzione `f` tramite una matrice `array` , restituendo `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="f23ab-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="f23ab-106">Input</span><span class="sxs-lookup"><span data-stu-id="f23ab-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="f23ab-107">cartella: (' stato,' non)-stato >'</span><span class="sxs-lookup"><span data-stu-id="f23ab-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="f23ab-108">Funzione da ripiegare sulla matrice.</span><span class="sxs-lookup"><span data-stu-id="f23ab-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="f23ab-109">stato:' stato</span><span class="sxs-lookup"><span data-stu-id="f23ab-109">state : 'State</span></span>

<span data-ttu-id="f23ab-110">Stato iniziale della cartella.</span><span class="sxs-lookup"><span data-stu-id="f23ab-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="f23ab-111">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="f23ab-111">array : 'T[]</span></span>

<span data-ttu-id="f23ab-112">Matrice di valori da ripiegare.</span><span class="sxs-lookup"><span data-stu-id="f23ab-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="f23ab-113">Output:' stato</span><span class="sxs-lookup"><span data-stu-id="f23ab-113">Output : 'State</span></span>

<span data-ttu-id="f23ab-114">Stato finale restituito dalla cartella dopo l'iterazione su tutti gli elementi di `array` .</span><span class="sxs-lookup"><span data-stu-id="f23ab-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f23ab-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f23ab-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="f23ab-116">' Stato</span><span class="sxs-lookup"><span data-stu-id="f23ab-116">'State</span></span>

<span data-ttu-id="f23ab-117">Tipo di stati `folder` su cui opera la funzione, ovvero accetta come primo argomento e restituisce.</span><span class="sxs-lookup"><span data-stu-id="f23ab-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="f23ab-118">T</span><span class="sxs-lookup"><span data-stu-id="f23ab-118">'T</span></span>

<span data-ttu-id="f23ab-119">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="f23ab-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="f23ab-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="f23ab-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```
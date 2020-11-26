---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220417"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="1f4af-102">RectangularArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="1f4af-102">RectangularArrayFact function</span></span>

<span data-ttu-id="1f4af-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1f4af-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1f4af-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f4af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f4af-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma rettangolare</span><span class="sxs-lookup"><span data-stu-id="1f4af-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="1f4af-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f4af-106">Description</span></span>

<span data-ttu-id="1f4af-107">Questa funzione dichiara che ogni riga in una matrice ha la stessa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="1f4af-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="1f4af-108">Input</span><span class="sxs-lookup"><span data-stu-id="1f4af-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="1f4af-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="1f4af-109">array : 'T[][]</span></span>

<span data-ttu-id="1f4af-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="1f4af-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="1f4af-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1f4af-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1f4af-112">Messaggio da stampare se la matrice non è una matrice rettangolare</span><span class="sxs-lookup"><span data-stu-id="1f4af-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f4af-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f4af-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f4af-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1f4af-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f4af-115">T</span><span class="sxs-lookup"><span data-stu-id="1f4af-115">'T</span></span>

<span data-ttu-id="1f4af-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="1f4af-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f4af-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f4af-117">See Also</span></span>

- [<span data-ttu-id="1f4af-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="1f4af-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)
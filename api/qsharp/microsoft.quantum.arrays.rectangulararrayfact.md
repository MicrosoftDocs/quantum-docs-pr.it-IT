---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845498"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="1a9f6-102">RectangularArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-102">RectangularArrayFact function</span></span>

<span data-ttu-id="1a9f6-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1a9f6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a9f6-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma rettangolare</span><span class="sxs-lookup"><span data-stu-id="1a9f6-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="1a9f6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a9f6-106">Description</span></span>

<span data-ttu-id="1a9f6-107">Questa funzione dichiara che ogni riga in una matrice ha la stessa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="1a9f6-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="1a9f6-108">Input</span><span class="sxs-lookup"><span data-stu-id="1a9f6-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="1a9f6-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="1a9f6-109">array : 'T[][]</span></span>

<span data-ttu-id="1a9f6-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="1a9f6-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="1a9f6-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1a9f6-112">Messaggio da stampare se la matrice non è una matrice rettangolare</span><span class="sxs-lookup"><span data-stu-id="1a9f6-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="1a9f6-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a9f6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1a9f6-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1a9f6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a9f6-115">T</span><span class="sxs-lookup"><span data-stu-id="1a9f6-115">'T</span></span>

<span data-ttu-id="1a9f6-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="1a9f6-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="1a9f6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a9f6-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="1a9f6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a9f6-118">See Also</span></span>

- [<span data-ttu-id="1a9f6-119">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="1a9f6-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)
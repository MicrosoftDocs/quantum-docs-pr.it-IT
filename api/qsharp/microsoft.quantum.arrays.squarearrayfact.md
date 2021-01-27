---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850973"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="bcf71-102">SquareArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="bcf71-102">SquareArrayFact function</span></span>

<span data-ttu-id="bcf71-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bcf71-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bcf71-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcf71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcf71-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma quadrata</span><span class="sxs-lookup"><span data-stu-id="bcf71-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="bcf71-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcf71-106">Description</span></span>

<span data-ttu-id="bcf71-107">Questa funzione asserisce che ogni riga in una matrice contiene tutti gli elementi presenti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="bcf71-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="bcf71-108">Input</span><span class="sxs-lookup"><span data-stu-id="bcf71-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bcf71-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="bcf71-109">array : 'T[][]</span></span>

<span data-ttu-id="bcf71-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="bcf71-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="bcf71-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bcf71-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bcf71-112">Messaggio da stampare se la matrice non è una matrice quadrata</span><span class="sxs-lookup"><span data-stu-id="bcf71-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="bcf71-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcf71-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bcf71-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bcf71-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bcf71-115">T</span><span class="sxs-lookup"><span data-stu-id="bcf71-115">'T</span></span>

<span data-ttu-id="bcf71-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="bcf71-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="bcf71-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="bcf71-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="bcf71-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcf71-118">See Also</span></span>

- [<span data-ttu-id="bcf71-119">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="bcf71-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)
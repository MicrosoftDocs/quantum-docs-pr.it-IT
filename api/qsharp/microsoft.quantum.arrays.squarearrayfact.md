---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220196"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="d8dbe-102">SquareArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-102">SquareArrayFact function</span></span>

<span data-ttu-id="d8dbe-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d8dbe-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8dbe-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma quadrata</span><span class="sxs-lookup"><span data-stu-id="d8dbe-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="d8dbe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8dbe-106">Description</span></span>

<span data-ttu-id="d8dbe-107">Questa funzione asserisce che ogni riga in una matrice contiene tutti gli elementi presenti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="d8dbe-108">Input</span><span class="sxs-lookup"><span data-stu-id="d8dbe-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d8dbe-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="d8dbe-109">array : 'T[][]</span></span>

<span data-ttu-id="d8dbe-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="d8dbe-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="d8dbe-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d8dbe-112">Messaggio da stampare se la matrice non è una matrice quadrata</span><span class="sxs-lookup"><span data-stu-id="d8dbe-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8dbe-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d8dbe-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d8dbe-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8dbe-115">T</span><span class="sxs-lookup"><span data-stu-id="d8dbe-115">'T</span></span>

<span data-ttu-id="d8dbe-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="d8dbe-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8dbe-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8dbe-117">See Also</span></span>

- [<span data-ttu-id="d8dbe-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="d8dbe-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)
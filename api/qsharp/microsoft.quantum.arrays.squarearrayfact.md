---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718854"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="15c3a-102">SquareArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="15c3a-102">SquareArrayFact function</span></span>

<span data-ttu-id="15c3a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="15c3a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="15c3a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15c3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15c3a-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma quadrata</span><span class="sxs-lookup"><span data-stu-id="15c3a-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="15c3a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15c3a-106">Description</span></span>

<span data-ttu-id="15c3a-107">Questa funzione asserisce che ogni riga in una matrice contiene tutti gli elementi presenti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="15c3a-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="15c3a-108">Input</span><span class="sxs-lookup"><span data-stu-id="15c3a-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="15c3a-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="15c3a-109">array : 'T[][]</span></span>

<span data-ttu-id="15c3a-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="15c3a-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="15c3a-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="15c3a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="15c3a-112">Messaggio da stampare se la matrice non è una matrice quadrata</span><span class="sxs-lookup"><span data-stu-id="15c3a-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="15c3a-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15c3a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15c3a-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="15c3a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15c3a-115">T</span><span class="sxs-lookup"><span data-stu-id="15c3a-115">'T</span></span>

<span data-ttu-id="15c3a-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="15c3a-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="15c3a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c3a-117">See Also</span></span>

- [<span data-ttu-id="15c3a-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="15c3a-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)
---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718923"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="47b6a-102">RectangularArrayFact (funzione)</span><span class="sxs-lookup"><span data-stu-id="47b6a-102">RectangularArrayFact function</span></span>

<span data-ttu-id="47b6a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="47b6a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="47b6a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47b6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47b6a-105">Rappresenta una condizione in cui una matrice bidimensionale ha una forma rettangolare</span><span class="sxs-lookup"><span data-stu-id="47b6a-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="47b6a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47b6a-106">Description</span></span>

<span data-ttu-id="47b6a-107">Questa funzione dichiara che ogni riga in una matrice ha la stessa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="47b6a-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="47b6a-108">Input</span><span class="sxs-lookup"><span data-stu-id="47b6a-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="47b6a-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="47b6a-109">array : 'T[][]</span></span>

<span data-ttu-id="47b6a-110">Matrice bidimensionale di elementi</span><span class="sxs-lookup"><span data-stu-id="47b6a-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="47b6a-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="47b6a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="47b6a-112">Messaggio da stampare se la matrice non è una matrice rettangolare</span><span class="sxs-lookup"><span data-stu-id="47b6a-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="47b6a-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47b6a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47b6a-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="47b6a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47b6a-115">T</span><span class="sxs-lookup"><span data-stu-id="47b6a-115">'T</span></span>

<span data-ttu-id="47b6a-116">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="47b6a-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="47b6a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47b6a-117">See Also</span></span>

- [<span data-ttu-id="47b6a-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="47b6a-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)
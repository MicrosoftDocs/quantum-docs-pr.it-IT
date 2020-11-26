---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220944"
---
# <a name="indexrange-function"></a><span data-ttu-id="32ddd-102">IndexRange (funzione)</span><span class="sxs-lookup"><span data-stu-id="32ddd-102">IndexRange function</span></span>

<span data-ttu-id="32ddd-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="32ddd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="32ddd-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="32ddd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="32ddd-105">Data una matrice, restituisce un intervallo sugli indici di tale matrice, adatto per l'uso in un ciclo for.</span><span class="sxs-lookup"><span data-stu-id="32ddd-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="32ddd-106">Input</span><span class="sxs-lookup"><span data-stu-id="32ddd-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="32ddd-107">matrice:' TElement []</span><span class="sxs-lookup"><span data-stu-id="32ddd-107">array : 'TElement[]</span></span>

<span data-ttu-id="32ddd-108">Matrice per la quale deve essere restituito un intervallo di indici.</span><span class="sxs-lookup"><span data-stu-id="32ddd-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="32ddd-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="32ddd-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="32ddd-110">Un intervallo su tutti gli indici della matrice.</span><span class="sxs-lookup"><span data-stu-id="32ddd-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32ddd-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="32ddd-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="32ddd-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="32ddd-112">'TElement</span></span>

<span data-ttu-id="32ddd-113">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="32ddd-113">The type of elements of the array.</span></span>
---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845787"
---
# <a name="indexrange-function"></a><span data-ttu-id="abda4-102">IndexRange (funzione)</span><span class="sxs-lookup"><span data-stu-id="abda4-102">IndexRange function</span></span>

<span data-ttu-id="abda4-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="abda4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="abda4-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="abda4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="abda4-105">Data una matrice, restituisce un intervallo sugli indici di tale matrice, adatto per l'uso in un ciclo for.</span><span class="sxs-lookup"><span data-stu-id="abda4-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="abda4-106">Input</span><span class="sxs-lookup"><span data-stu-id="abda4-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="abda4-107">matrice:' TElement []</span><span class="sxs-lookup"><span data-stu-id="abda4-107">array : 'TElement[]</span></span>

<span data-ttu-id="abda4-108">Matrice per la quale deve essere restituito un intervallo di indici.</span><span class="sxs-lookup"><span data-stu-id="abda4-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="abda4-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="abda4-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="abda4-110">Un intervallo su tutti gli indici della matrice.</span><span class="sxs-lookup"><span data-stu-id="abda4-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="abda4-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="abda4-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="abda4-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="abda4-112">'TElement</span></span>

<span data-ttu-id="abda4-113">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="abda4-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="abda4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="abda4-114">Example</span></span>

<span data-ttu-id="abda4-115">I `for` cicli seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="abda4-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```
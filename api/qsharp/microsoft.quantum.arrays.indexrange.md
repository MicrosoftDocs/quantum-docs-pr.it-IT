---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719151"
---
# <a name="indexrange-function"></a><span data-ttu-id="db339-102">IndexRange (funzione)</span><span class="sxs-lookup"><span data-stu-id="db339-102">IndexRange function</span></span>

<span data-ttu-id="db339-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db339-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db339-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db339-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db339-105">Data una matrice, restituisce un intervallo sugli indici di tale matrice, adatto per l'uso in un ciclo for.</span><span class="sxs-lookup"><span data-stu-id="db339-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="db339-106">Input</span><span class="sxs-lookup"><span data-stu-id="db339-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="db339-107">matrice:' TElement []</span><span class="sxs-lookup"><span data-stu-id="db339-107">array : 'TElement[]</span></span>

<span data-ttu-id="db339-108">Matrice per la quale deve essere restituito un intervallo di indici.</span><span class="sxs-lookup"><span data-stu-id="db339-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="db339-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="db339-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="db339-110">Un intervallo su tutti gli indici della matrice.</span><span class="sxs-lookup"><span data-stu-id="db339-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db339-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="db339-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="db339-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="db339-112">'TElement</span></span>

<span data-ttu-id="db339-113">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="db339-113">The type of elements of the array.</span></span>
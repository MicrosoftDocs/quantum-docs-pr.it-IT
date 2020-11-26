---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210099"
---
# <a name="columnat-function"></a><span data-ttu-id="197c4-102">ColumnAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="197c4-102">ColumnAt function</span></span>

<span data-ttu-id="197c4-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="197c4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="197c4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="197c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="197c4-105">Estrae una colonna da una matrice.</span><span class="sxs-lookup"><span data-stu-id="197c4-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="197c4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="197c4-106">Description</span></span>

<span data-ttu-id="197c4-107">Questa funzione estrae una colonna in una matrice in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="197c4-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="197c4-108">L'estrazione di una riga corrsponds nell'accesso agli elementi del primo indice e pertanto non richiede alcun ulteriore trattamento.</span><span class="sxs-lookup"><span data-stu-id="197c4-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="197c4-109">Input</span><span class="sxs-lookup"><span data-stu-id="197c4-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="197c4-110">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="197c4-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="197c4-111">Colonna della matrice</span><span class="sxs-lookup"><span data-stu-id="197c4-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="197c4-112">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="197c4-112">matrix : 'T[][]</span></span>

<span data-ttu-id="197c4-113">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="197c4-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="197c4-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="197c4-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="197c4-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="197c4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="197c4-116">T</span><span class="sxs-lookup"><span data-stu-id="197c4-116">'T</span></span>

<span data-ttu-id="197c4-117">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="197c4-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="197c4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="197c4-118">See Also</span></span>

- [<span data-ttu-id="197c4-119">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="197c4-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="197c4-120">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="197c4-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)
---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846264"
---
# <a name="columnat-function"></a><span data-ttu-id="89241-102">ColumnAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="89241-102">ColumnAt function</span></span>

<span data-ttu-id="89241-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="89241-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="89241-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89241-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89241-105">Estrae una colonna da una matrice.</span><span class="sxs-lookup"><span data-stu-id="89241-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="89241-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89241-106">Description</span></span>

<span data-ttu-id="89241-107">Questa funzione estrae una colonna in una matrice in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="89241-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="89241-108">L'estrazione di una riga corrsponds nell'accesso agli elementi del primo indice e pertanto non richiede alcun ulteriore trattamento.</span><span class="sxs-lookup"><span data-stu-id="89241-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="89241-109">Input</span><span class="sxs-lookup"><span data-stu-id="89241-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="89241-110">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89241-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89241-111">Colonna della matrice</span><span class="sxs-lookup"><span data-stu-id="89241-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="89241-112">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="89241-112">matrix : 'T[][]</span></span>

<span data-ttu-id="89241-113">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="89241-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="89241-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="89241-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="89241-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="89241-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89241-116">T</span><span class="sxs-lookup"><span data-stu-id="89241-116">'T</span></span>

<span data-ttu-id="89241-117">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="89241-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="89241-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="89241-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="89241-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89241-119">See Also</span></span>

- [<span data-ttu-id="89241-120">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="89241-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="89241-121">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="89241-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)
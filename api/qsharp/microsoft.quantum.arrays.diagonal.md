---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842820"
---
# <a name="diagonal-function"></a><span data-ttu-id="0e0e0-102">Diagonal (funzione)</span><span class="sxs-lookup"><span data-stu-id="0e0e0-102">Diagonal function</span></span>

<span data-ttu-id="0e0e0-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0e0e0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0e0e0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e0e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e0e0-105">Restituisce una matrice di elementi diagonali di una matrice bidimensionale</span><span class="sxs-lookup"><span data-stu-id="0e0e0-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="0e0e0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e0e0-106">Description</span></span>

<span data-ttu-id="0e0e0-107">Se la matrice bidimensionale non ha una forma quadrata, verrà restituita la diagonale sopra il numero minimo di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="0e0e0-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="0e0e0-108">Input</span><span class="sxs-lookup"><span data-stu-id="0e0e0-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="0e0e0-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="0e0e0-109">matrix : 'T[][]</span></span>

<span data-ttu-id="0e0e0-110">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="0e0e0-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="0e0e0-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="0e0e0-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0e0e0-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0e0e0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e0e0-113">T</span><span class="sxs-lookup"><span data-stu-id="0e0e0-113">'T</span></span>

<span data-ttu-id="0e0e0-114">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="0e0e0-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="0e0e0-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e0e0-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="0e0e0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0e0-116">See Also</span></span>

- [<span data-ttu-id="0e0e0-117">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="0e0e0-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
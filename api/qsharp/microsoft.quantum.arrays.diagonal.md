---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221539"
---
# <a name="diagonal-function"></a><span data-ttu-id="62ff5-102">Diagonal (funzione)</span><span class="sxs-lookup"><span data-stu-id="62ff5-102">Diagonal function</span></span>

<span data-ttu-id="62ff5-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="62ff5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="62ff5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62ff5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62ff5-105">Restituisce una matrice di elementi diagonali di una matrice bidimensionale</span><span class="sxs-lookup"><span data-stu-id="62ff5-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="62ff5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62ff5-106">Description</span></span>

<span data-ttu-id="62ff5-107">Se la matrice bidimensionale non ha una forma quadrata, verrà restituita la diagonale sopra il numero minimo di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="62ff5-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="62ff5-108">Input</span><span class="sxs-lookup"><span data-stu-id="62ff5-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="62ff5-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="62ff5-109">matrix : 'T[][]</span></span>

<span data-ttu-id="62ff5-110">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="62ff5-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="62ff5-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="62ff5-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="62ff5-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="62ff5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="62ff5-113">T</span><span class="sxs-lookup"><span data-stu-id="62ff5-113">'T</span></span>

<span data-ttu-id="62ff5-114">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="62ff5-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ff5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ff5-115">See Also</span></span>

- [<span data-ttu-id="62ff5-116">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="62ff5-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
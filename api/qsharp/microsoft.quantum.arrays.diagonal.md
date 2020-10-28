---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719382"
---
# <a name="diagonal-function"></a><span data-ttu-id="95350-102">Diagonal (funzione)</span><span class="sxs-lookup"><span data-stu-id="95350-102">Diagonal function</span></span>

<span data-ttu-id="95350-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95350-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95350-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95350-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95350-105">Restituisce una matrice di elementi diagonali di una matrice bidimensionale</span><span class="sxs-lookup"><span data-stu-id="95350-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="95350-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95350-106">Description</span></span>

<span data-ttu-id="95350-107">Se la matrice bidimensionale non ha una forma quadrata, verrà restituita la diagonale sopra il numero minimo di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="95350-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="95350-108">Input</span><span class="sxs-lookup"><span data-stu-id="95350-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="95350-109">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="95350-109">matrix : 'T[][]</span></span>

<span data-ttu-id="95350-110">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="95350-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="95350-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="95350-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95350-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="95350-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95350-113">T</span><span class="sxs-lookup"><span data-stu-id="95350-113">'T</span></span>

<span data-ttu-id="95350-114">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="95350-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="95350-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95350-115">See Also</span></span>

- [<span data-ttu-id="95350-116">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="95350-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
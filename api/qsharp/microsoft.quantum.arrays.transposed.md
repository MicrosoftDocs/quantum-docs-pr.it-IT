---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funzione trasposta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718815"
---
# <a name="transposed-function"></a><span data-ttu-id="f56d8-102">Funzione trasposta</span><span class="sxs-lookup"><span data-stu-id="f56d8-102">Transposed function</span></span>

<span data-ttu-id="f56d8-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f56d8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f56d8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f56d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f56d8-105">Restituisce la trasposta di una matrice rappresentata come matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="f56d8-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="f56d8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f56d8-106">Description</span></span>

<span data-ttu-id="f56d8-107">Input come $r \times c $ Matrix con $r $ Rows e $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="f56d8-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="f56d8-108">La matrice è basata su righe, ad esempio, `matrix[i][j]` accede all'elemento alla riga $i $ e alla colonna $j $.</span><span class="sxs-lookup"><span data-stu-id="f56d8-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="f56d8-109">Questa funzione restituisce la $c \times r $ Matrix che rappresenta la traspone della matrice di input.</span><span class="sxs-lookup"><span data-stu-id="f56d8-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="f56d8-110">Input</span><span class="sxs-lookup"><span data-stu-id="f56d8-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="f56d8-111">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="f56d8-111">matrix : 'T[][]</span></span>

<span data-ttu-id="f56d8-112">Tabella $r \times c $ Matrix basata su righe</span><span class="sxs-lookup"><span data-stu-id="f56d8-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="f56d8-113">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="f56d8-113">Output : 'T[][]</span></span>

<span data-ttu-id="f56d8-114">Transposed $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="f56d8-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f56d8-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f56d8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f56d8-116">T</span><span class="sxs-lookup"><span data-stu-id="f56d8-116">'T</span></span>

<span data-ttu-id="f56d8-117">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="f56d8-117">The type of each element of `matrix`.</span></span>
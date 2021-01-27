---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funzione trasposta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850942"
---
# <a name="transposed-function"></a><span data-ttu-id="c4207-102">Funzione trasposta</span><span class="sxs-lookup"><span data-stu-id="c4207-102">Transposed function</span></span>

<span data-ttu-id="c4207-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4207-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4207-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4207-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4207-105">Restituisce la trasposta di una matrice rappresentata come matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="c4207-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="c4207-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4207-106">Description</span></span>

<span data-ttu-id="c4207-107">Input come $r \times c $ Matrix con $r $ Rows e $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="c4207-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="c4207-108">La matrice è basata su righe, ad esempio, `matrix[i][j]` accede all'elemento alla riga $i $ e alla colonna $j $.</span><span class="sxs-lookup"><span data-stu-id="c4207-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="c4207-109">Questa funzione restituisce la $c \times r $ Matrix che rappresenta la traspone della matrice di input.</span><span class="sxs-lookup"><span data-stu-id="c4207-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="c4207-110">Input</span><span class="sxs-lookup"><span data-stu-id="c4207-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="c4207-111">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="c4207-111">matrix : 'T[][]</span></span>

<span data-ttu-id="c4207-112">Tabella $r \times c $ Matrix basata su righe</span><span class="sxs-lookup"><span data-stu-id="c4207-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="c4207-113">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="c4207-113">Output : 'T[][]</span></span>

<span data-ttu-id="c4207-114">Transposed $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="c4207-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4207-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c4207-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4207-116">T</span><span class="sxs-lookup"><span data-stu-id="c4207-116">'T</span></span>

<span data-ttu-id="c4207-117">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="c4207-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="c4207-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4207-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```
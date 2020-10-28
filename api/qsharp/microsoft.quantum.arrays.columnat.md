---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719454"
---
# <a name="columnat-function"></a><span data-ttu-id="5688f-102">ColumnAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="5688f-102">ColumnAt function</span></span>

<span data-ttu-id="5688f-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5688f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5688f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5688f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5688f-105">Estrae una colonna da una matrice.</span><span class="sxs-lookup"><span data-stu-id="5688f-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="5688f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5688f-106">Description</span></span>

<span data-ttu-id="5688f-107">Questa funzione estrae una colonna in una matrice in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="5688f-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="5688f-108">L'estrazione di una riga corrsponds nell'accesso agli elementi del primo indice e pertanto non richiede alcun ulteriore trattamento.</span><span class="sxs-lookup"><span data-stu-id="5688f-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="5688f-109">Input</span><span class="sxs-lookup"><span data-stu-id="5688f-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="5688f-110">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5688f-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5688f-111">Colonna della matrice</span><span class="sxs-lookup"><span data-stu-id="5688f-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="5688f-112">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="5688f-112">matrix : 'T[][]</span></span>

<span data-ttu-id="5688f-113">matrice bidimensionale in ordine per riga</span><span class="sxs-lookup"><span data-stu-id="5688f-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="5688f-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="5688f-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5688f-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5688f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5688f-116">T</span><span class="sxs-lookup"><span data-stu-id="5688f-116">'T</span></span>

<span data-ttu-id="5688f-117">Tipo di ogni elemento di `matrix` .</span><span class="sxs-lookup"><span data-stu-id="5688f-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5688f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5688f-118">See Also</span></span>

- [<span data-ttu-id="5688f-119">Microsoft. Quantum. Arrays. transposed</span><span class="sxs-lookup"><span data-stu-id="5688f-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="5688f-120">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="5688f-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)
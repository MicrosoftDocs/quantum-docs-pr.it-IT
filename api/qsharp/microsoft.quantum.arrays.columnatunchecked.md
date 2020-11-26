---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221590"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="5def5-102">ColumnAtUnchecked (funzione)</span><span class="sxs-lookup"><span data-stu-id="5def5-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="5def5-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5def5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5def5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5def5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5def5-105">Questa funzione non controlla la forma matrice</span><span class="sxs-lookup"><span data-stu-id="5def5-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="5def5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5def5-106">Description</span></span>

<span data-ttu-id="5def5-107">Questa funzione può essere utilizzata in altre funzioni multidimensionali che controllano già la matrice di input per una forma rettangolare valida.</span><span class="sxs-lookup"><span data-stu-id="5def5-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="5def5-108">Input</span><span class="sxs-lookup"><span data-stu-id="5def5-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="5def5-109">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5def5-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="5def5-110">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="5def5-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="5def5-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="5def5-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5def5-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5def5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5def5-113">T</span><span class="sxs-lookup"><span data-stu-id="5def5-113">'T</span></span>


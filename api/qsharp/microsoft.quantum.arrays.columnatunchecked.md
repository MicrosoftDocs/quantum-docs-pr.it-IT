---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719451"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="28dba-102">ColumnAtUnchecked (funzione)</span><span class="sxs-lookup"><span data-stu-id="28dba-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="28dba-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="28dba-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="28dba-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28dba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28dba-105">Questa funzione non controlla la forma matrice</span><span class="sxs-lookup"><span data-stu-id="28dba-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="28dba-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28dba-106">Description</span></span>

<span data-ttu-id="28dba-107">Questa funzione può essere utilizzata in altre funzioni multidimensionali che controllano già la matrice di input per una forma rettangolare valida.</span><span class="sxs-lookup"><span data-stu-id="28dba-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="28dba-108">Input</span><span class="sxs-lookup"><span data-stu-id="28dba-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="28dba-109">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28dba-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="28dba-110">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="28dba-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="28dba-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="28dba-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28dba-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="28dba-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28dba-113">T</span><span class="sxs-lookup"><span data-stu-id="28dba-113">'T</span></span>


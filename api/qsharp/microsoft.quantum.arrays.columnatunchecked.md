---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842868"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="8ffad-102">ColumnAtUnchecked (funzione)</span><span class="sxs-lookup"><span data-stu-id="8ffad-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="8ffad-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ffad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ffad-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ffad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ffad-105">Questa funzione non controlla la forma matrice</span><span class="sxs-lookup"><span data-stu-id="8ffad-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="8ffad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ffad-106">Description</span></span>

<span data-ttu-id="8ffad-107">Questa funzione può essere utilizzata in altre funzioni multidimensionali che controllano già la matrice di input per una forma rettangolare valida.</span><span class="sxs-lookup"><span data-stu-id="8ffad-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="8ffad-108">Input</span><span class="sxs-lookup"><span data-stu-id="8ffad-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="8ffad-109">colonna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ffad-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="8ffad-110">matrice:' t [] []</span><span class="sxs-lookup"><span data-stu-id="8ffad-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="8ffad-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="8ffad-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ffad-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8ffad-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ffad-113">T</span><span class="sxs-lookup"><span data-stu-id="8ffad-113">'T</span></span>


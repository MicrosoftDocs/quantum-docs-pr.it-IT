---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funzione enumerata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848132"
---
# <a name="enumerated-function"></a><span data-ttu-id="0a9f8-102">Funzione enumerata</span><span class="sxs-lookup"><span data-stu-id="0a9f8-102">Enumerated function</span></span>

<span data-ttu-id="0a9f8-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0a9f8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0a9f8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a9f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a9f8-105">Data una matrice, restituisce una nuova matrice contenente gli elementi della matrice originale insieme agli indici di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="0a9f8-106">Input</span><span class="sxs-lookup"><span data-stu-id="0a9f8-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="0a9f8-107">matrice:' TElement []</span><span class="sxs-lookup"><span data-stu-id="0a9f8-107">array : 'TElement[]</span></span>

<span data-ttu-id="0a9f8-108">Matrice i cui elementi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="0a9f8-109">Output: ([int](xref:microsoft.quantum.lang-ref.int),' TElement) []</span><span class="sxs-lookup"><span data-stu-id="0a9f8-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="0a9f8-110">Nuova matrice contenente gli elementi della matrice originale insieme ai relativi indici.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a9f8-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0a9f8-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="0a9f8-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="0a9f8-112">'TElement</span></span>

<span data-ttu-id="0a9f8-113">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="0a9f8-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a9f8-114">Example</span></span>

<span data-ttu-id="0a9f8-115">I `for` cicli seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="0a9f8-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```
---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220077"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="e217b-102">TupleArrayAsNestedArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="e217b-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="e217b-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e217b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e217b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e217b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e217b-105">Converte un elenco di due tuple in una matrice annidata.</span><span class="sxs-lookup"><span data-stu-id="e217b-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e217b-106">Input</span><span class="sxs-lookup"><span data-stu-id="e217b-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="e217b-107">tupla: (t, t) []</span><span class="sxs-lookup"><span data-stu-id="e217b-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="e217b-108">Elenco di due tuple da trasformare in una matrice annidata.</span><span class="sxs-lookup"><span data-stu-id="e217b-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e217b-109">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="e217b-109">Output : 'T[][]</span></span>

<span data-ttu-id="e217b-110">Matrice annidata con lunghezza corrispondente a Tuple.</span><span class="sxs-lookup"><span data-stu-id="e217b-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="e217b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e217b-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="e217b-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e217b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e217b-113">T</span><span class="sxs-lookup"><span data-stu-id="e217b-113">'T</span></span>


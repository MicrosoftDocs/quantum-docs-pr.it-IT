---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718806"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="39d4e-102">TupleArrayAsNestedArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="39d4e-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="39d4e-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39d4e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39d4e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39d4e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39d4e-105">Converte un elenco di due tuple in una matrice annidata.</span><span class="sxs-lookup"><span data-stu-id="39d4e-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="39d4e-106">Input</span><span class="sxs-lookup"><span data-stu-id="39d4e-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="39d4e-107">tupla: (t, t) []</span><span class="sxs-lookup"><span data-stu-id="39d4e-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="39d4e-108">Elenco di due tuple da trasformare in una matrice annidata.</span><span class="sxs-lookup"><span data-stu-id="39d4e-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="39d4e-109">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="39d4e-109">Output : 'T[][]</span></span>

<span data-ttu-id="39d4e-110">Matrice annidata con lunghezza corrispondente a Tuple.</span><span class="sxs-lookup"><span data-stu-id="39d4e-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="39d4e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="39d4e-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="39d4e-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="39d4e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39d4e-113">T</span><span class="sxs-lookup"><span data-stu-id="39d4e-113">'T</span></span>


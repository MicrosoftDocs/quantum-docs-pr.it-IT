---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210064"
---
# <a name="constantarray-function"></a><span data-ttu-id="95e92-102">ConstantArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="95e92-102">ConstantArray function</span></span>

<span data-ttu-id="95e92-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95e92-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95e92-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95e92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95e92-105">Crea una matrice di lunghezza specificata con tutti gli elementi uguali al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="95e92-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="95e92-106">Input</span><span class="sxs-lookup"><span data-stu-id="95e92-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="95e92-107">Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95e92-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95e92-108">Lunghezza della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="95e92-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="95e92-109">valore:' t</span><span class="sxs-lookup"><span data-stu-id="95e92-109">value : 'T</span></span>

<span data-ttu-id="95e92-110">Valore di ogni elemento della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="95e92-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="95e92-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="95e92-111">Output : 'T[]</span></span>

<span data-ttu-id="95e92-112">Una nuova matrice di lunghezza `length` , in modo che ogni elemento sia `value` .</span><span class="sxs-lookup"><span data-stu-id="95e92-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95e92-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="95e92-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95e92-114">T</span><span class="sxs-lookup"><span data-stu-id="95e92-114">'T</span></span>


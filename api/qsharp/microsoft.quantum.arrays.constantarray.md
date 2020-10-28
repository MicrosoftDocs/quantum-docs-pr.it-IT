---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719415"
---
# <a name="constantarray-function"></a><span data-ttu-id="fc8de-102">ConstantArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="fc8de-102">ConstantArray function</span></span>

<span data-ttu-id="fc8de-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc8de-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc8de-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc8de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc8de-105">Crea una matrice di lunghezza specificata con tutti gli elementi uguali al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="fc8de-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fc8de-106">Input</span><span class="sxs-lookup"><span data-stu-id="fc8de-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="fc8de-107">Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc8de-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc8de-108">Lunghezza della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="fc8de-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="fc8de-109">valore:' t</span><span class="sxs-lookup"><span data-stu-id="fc8de-109">value : 'T</span></span>

<span data-ttu-id="fc8de-110">Valore di ogni elemento della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="fc8de-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="fc8de-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="fc8de-111">Output : 'T[]</span></span>

<span data-ttu-id="fc8de-112">Una nuova matrice di lunghezza `length` , in modo che ogni elemento sia `value` .</span><span class="sxs-lookup"><span data-stu-id="fc8de-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc8de-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="fc8de-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc8de-114">T</span><span class="sxs-lookup"><span data-stu-id="fc8de-114">'T</span></span>


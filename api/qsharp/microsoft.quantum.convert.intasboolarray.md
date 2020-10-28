---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713457"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="92b02-102">IntAsBoolArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="92b02-102">IntAsBoolArray function</span></span>

<span data-ttu-id="92b02-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="92b02-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="92b02-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92b02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92b02-105">Produce una rappresentazione binaria di un intero positivo, usando la rappresentazione little-endian per la matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="92b02-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="92b02-106">Input</span><span class="sxs-lookup"><span data-stu-id="92b02-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="92b02-107">numero: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92b02-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92b02-108">Intero positivo da convertire in una matrice di valori booleani.</span><span class="sxs-lookup"><span data-stu-id="92b02-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="92b02-109">bit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92b02-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92b02-110">Numero di bit nella rappresentazione binaria di `number` .</span><span class="sxs-lookup"><span data-stu-id="92b02-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="92b02-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="92b02-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="92b02-112">Matrice di valori booleani che rappresentano `number` .</span><span class="sxs-lookup"><span data-stu-id="92b02-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="92b02-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="92b02-113">Remarks</span></span>

<span data-ttu-id="92b02-114">L'input `bits` deve essere compreso tra 0 e 63.</span><span class="sxs-lookup"><span data-stu-id="92b02-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="92b02-115">L'input `number` deve essere compreso tra 0 e $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="92b02-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>
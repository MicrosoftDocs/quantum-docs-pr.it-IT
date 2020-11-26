---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224344"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="0ec63-102">IntAsBoolArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="0ec63-102">IntAsBoolArray function</span></span>

<span data-ttu-id="0ec63-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0ec63-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0ec63-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ec63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ec63-105">Produce una rappresentazione binaria di un intero positivo, usando la rappresentazione little-endian per la matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0ec63-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="0ec63-106">Input</span><span class="sxs-lookup"><span data-stu-id="0ec63-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="0ec63-107">numero: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ec63-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ec63-108">Intero positivo da convertire in una matrice di valori booleani.</span><span class="sxs-lookup"><span data-stu-id="0ec63-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="0ec63-109">bit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ec63-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ec63-110">Numero di bit nella rappresentazione binaria di `number` .</span><span class="sxs-lookup"><span data-stu-id="0ec63-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0ec63-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0ec63-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0ec63-112">Matrice di valori booleani che rappresentano `number` .</span><span class="sxs-lookup"><span data-stu-id="0ec63-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ec63-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="0ec63-113">Remarks</span></span>

<span data-ttu-id="0ec63-114">L'input `bits` deve essere compreso tra 0 e 63.</span><span class="sxs-lookup"><span data-stu-id="0ec63-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="0ec63-115">L'input `number` deve essere compreso tra 0 e $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="0ec63-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>
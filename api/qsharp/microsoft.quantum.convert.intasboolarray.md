---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833313"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="07f94-102">IntAsBoolArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="07f94-102">IntAsBoolArray function</span></span>

<span data-ttu-id="07f94-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="07f94-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="07f94-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07f94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07f94-105">Produce una rappresentazione binaria di un numero intero non negativo, usando la rappresentazione little-endian per la matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="07f94-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="07f94-106">Input</span><span class="sxs-lookup"><span data-stu-id="07f94-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="07f94-107">numero: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07f94-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07f94-108">Intero non negativo da convertire in una matrice di valori booleani.</span><span class="sxs-lookup"><span data-stu-id="07f94-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="07f94-109">bit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07f94-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07f94-110">Numero di bit nella rappresentazione binaria di `number` .</span><span class="sxs-lookup"><span data-stu-id="07f94-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="07f94-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="07f94-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="07f94-112">Matrice di valori booleani che rappresentano `number` .</span><span class="sxs-lookup"><span data-stu-id="07f94-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="07f94-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="07f94-113">Remarks</span></span>

<span data-ttu-id="07f94-114">L'input `bits` deve essere compreso tra 0 e 63.</span><span class="sxs-lookup"><span data-stu-id="07f94-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="07f94-115">L'input `number` deve essere compreso tra 0 e $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="07f94-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>
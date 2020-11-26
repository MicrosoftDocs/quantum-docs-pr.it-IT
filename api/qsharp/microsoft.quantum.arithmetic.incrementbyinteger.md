---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operazione IncrementByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222967"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="5cc21-102">Operazione IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="5cc21-102">IncrementByInteger operation</span></span>

<span data-ttu-id="5cc21-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5cc21-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5cc21-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cc21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cc21-105">Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.</span><span class="sxs-lookup"><span data-stu-id="5cc21-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5cc21-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cc21-106">Description</span></span>

<span data-ttu-id="5cc21-107">Si supponga che `target` codifica un Unsigned Integer $x $ in una codifica little-endian e che `increment` sia uguale a $a $.</span><span class="sxs-lookup"><span data-stu-id="5cc21-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="5cc21-108">Questa operazione implementa quindi l'unità $ \ket{x} \mapsto \ket{x + a} $, in cui viene eseguita l'aggiunta modulo $2 ^ n $, dove $n = \texttt{Length (target!)} $.</span><span class="sxs-lookup"><span data-stu-id="5cc21-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="5cc21-109">Input</span><span class="sxs-lookup"><span data-stu-id="5cc21-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="5cc21-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cc21-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cc21-111">Integer in base al quale `target` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="5cc21-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="5cc21-112">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5cc21-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5cc21-113">Un registro Quantum che codifica un Unsigned Integer usando la codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="5cc21-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5cc21-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cc21-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operazione IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721110"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="d7119-102">Operazione IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="d7119-102">IncrementByInteger operation</span></span>

<span data-ttu-id="d7119-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7119-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7119-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7119-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7119-105">Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.</span><span class="sxs-lookup"><span data-stu-id="d7119-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d7119-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7119-106">Description</span></span>

<span data-ttu-id="d7119-107">Si supponga che `target` codifica un Unsigned Integer $x $ in una codifica little-endian e che `increment` sia uguale a $a $.</span><span class="sxs-lookup"><span data-stu-id="d7119-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="d7119-108">Questa operazione implementa quindi l'unità $ \ket{x} \mapsto \ket{x + a} $, in cui viene eseguita l'aggiunta modulo $2 ^ n $, dove $n = \texttt{Length (target!)} $.</span><span class="sxs-lookup"><span data-stu-id="d7119-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="d7119-109">Input</span><span class="sxs-lookup"><span data-stu-id="d7119-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="d7119-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7119-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7119-111">Integer in base al quale `target` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="d7119-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="d7119-112">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7119-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7119-113">Un registro Quantum che codifica un Unsigned Integer usando la codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="d7119-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7119-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7119-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


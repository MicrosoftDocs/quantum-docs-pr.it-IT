---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operazione IncrementPhaseByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721074"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="be9c0-102">Operazione IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="be9c0-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="be9c0-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="be9c0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="be9c0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be9c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be9c0-105">Incrementa un registro Quantum senza segno da un numero intero classico, usando le rotazioni della fase.</span><span class="sxs-lookup"><span data-stu-id="be9c0-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="be9c0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be9c0-106">Description</span></span>

<span data-ttu-id="be9c0-107">Si supponga che `target` codifica un Unsigned Integer $x $ in una codifica little-endian e che `increment` sia uguale a $a $.</span><span class="sxs-lookup"><span data-stu-id="be9c0-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="be9c0-108">Questa operazione implementa quindi l'unità $ \ket{x} \mapsto \ket{x + a} $, in cui viene eseguita l'aggiunta modulo $2 ^ n $, dove $n = \texttt{Length (target!)} $.</span><span class="sxs-lookup"><span data-stu-id="be9c0-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="be9c0-109">Input</span><span class="sxs-lookup"><span data-stu-id="be9c0-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="be9c0-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be9c0-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be9c0-111">Integer in base al quale `target` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="be9c0-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="be9c0-112">destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="be9c0-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="be9c0-113">Un registro Quantum codifica un Unsigned Integer usando la codifica little-endian nella doppia (QFT).</span><span class="sxs-lookup"><span data-stu-id="be9c0-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be9c0-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be9c0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="be9c0-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="be9c0-115">Remarks</span></span>

<span data-ttu-id="be9c0-116">Si noti che il circuito è stato semplificato perché l'incremento è una costante classica, non un registro quantico.</span><span class="sxs-lookup"><span data-stu-id="be9c0-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="be9c0-117">Vedere la figura della [ pagina 6 di arXiv: quanti-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) per la spiegazione e il diagramma del circuito.</span><span class="sxs-lookup"><span data-stu-id="be9c0-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="be9c0-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="be9c0-118">References</span></span>

- [<span data-ttu-id="be9c0-119">*Thomas G. Draper* , arXiv: quanti-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="be9c0-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="be9c0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be9c0-120">See Also</span></span>

- [<span data-ttu-id="be9c0-121">Microsoft. Quantum. aritmetic. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="be9c0-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)
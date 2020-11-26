---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operazione MultiplyAndAddByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222593"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="f46fd-102">Operazione MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="f46fd-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="f46fd-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f46fd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f46fd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f46fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f46fd-105">Esegue un valore modulare Multiply-and-Add per le costanti integer in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="f46fd-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f46fd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f46fd-106">Description</span></span>

<span data-ttu-id="f46fd-107">Implementa la mappa $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ per un modulo specificato $N $, il moltiplicatore costante $a $ e summand $y $.</span><span class="sxs-lookup"><span data-stu-id="f46fd-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="f46fd-108">Input</span><span class="sxs-lookup"><span data-stu-id="f46fd-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="f46fd-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f46fd-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f46fd-110">Integer $a $ da aggiungere a ogni etichetta di stato di base.</span><span class="sxs-lookup"><span data-stu-id="f46fd-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="f46fd-111">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f46fd-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f46fd-112">Il modulo $N $ quali addizioni e moltiplicazioni vengono prese in relazione a.</span><span class="sxs-lookup"><span data-stu-id="f46fd-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="f46fd-113">moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f46fd-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f46fd-114">Registro Quantum che rappresenta un Unsigned Integer il cui valore deve essere aggiunto a ogni etichetta dello stato di base di `summand` .</span><span class="sxs-lookup"><span data-stu-id="f46fd-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="f46fd-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f46fd-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f46fd-116">Registro Quantum che rappresenta un Unsigned Integer da usare come destinazione per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f46fd-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f46fd-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f46fd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f46fd-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="f46fd-118">Remarks</span></span>

- <span data-ttu-id="f46fd-119">Per il diagramma di circuito e la spiegazione, vedere la figura 6 sulla [pagina 7 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="f46fd-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="f46fd-120">Questa operazione corrisponde a CMULT (a) MOD (N) in [arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="f46fd-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="f46fd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f46fd-121">See Also</span></span>

- [<span data-ttu-id="f46fd-122">Microsoft. Quantum. aritmetic. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="f46fd-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)
---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operazione IncrementPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222882"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="e7b5c-102">Operazione IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e7b5c-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="e7b5c-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e7b5c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7b5c-105">Esegue un incremento modulare di un registro qubit da una costante Integer.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e7b5c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7b5c-106">Description</span></span>

<span data-ttu-id="e7b5c-107">È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="e7b5c-108">L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} i numeri interi sono codificati in formato little-endian in base a QFT.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="e7b5c-109">Input</span><span class="sxs-lookup"><span data-stu-id="e7b5c-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="e7b5c-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7b5c-111">Incremento Integer $a $ da aggiungere a $y $.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e7b5c-112">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7b5c-113">Integer $N $ che mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="e7b5c-114">destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e7b5c-115">Integer $y $ in formato little-endian con codifica fase `increment` a cui viene aggiunto $a $.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7b5c-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7b5c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e7b5c-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="e7b5c-117">Remarks</span></span>

<span data-ttu-id="e7b5c-118">Presuppone che `target` il bit più alto sia impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="e7b5c-119">Presuppone inoltre che il valore di target sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="e7b5c-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="e7b5c-120">Per il diagramma di circuito e la spiegazione, vedere la figura 5 [della pagina 5 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="e7b5c-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7b5c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7b5c-121">See Also</span></span>

- [<span data-ttu-id="e7b5c-122">Microsoft. Quantum. aritmetic. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e7b5c-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)
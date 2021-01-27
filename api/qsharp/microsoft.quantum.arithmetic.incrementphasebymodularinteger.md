---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operazione IncrementPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846586"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="8d2be-102">Operazione IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8d2be-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="8d2be-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8d2be-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8d2be-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d2be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d2be-105">Esegue un incremento modulare di un registro qubit da una costante Integer.</span><span class="sxs-lookup"><span data-stu-id="8d2be-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8d2be-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d2be-106">Description</span></span>

<span data-ttu-id="8d2be-107">È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.</span><span class="sxs-lookup"><span data-stu-id="8d2be-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="8d2be-108">L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} i numeri interi sono codificati in formato little-endian in base a QFT.</span><span class="sxs-lookup"><span data-stu-id="8d2be-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="8d2be-109">Input</span><span class="sxs-lookup"><span data-stu-id="8d2be-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="8d2be-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d2be-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d2be-111">Incremento Integer $a $ da aggiungere a $y $.</span><span class="sxs-lookup"><span data-stu-id="8d2be-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8d2be-112">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d2be-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d2be-113">Integer $N $ che mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="8d2be-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="8d2be-114">destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8d2be-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="8d2be-115">Integer $y $ in formato little-endian con codifica fase `increment` a cui viene aggiunto $a $.</span><span class="sxs-lookup"><span data-stu-id="8d2be-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d2be-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d2be-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d2be-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="8d2be-117">Remarks</span></span>

<span data-ttu-id="8d2be-118">Presuppone che `target` il bit più alto sia impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="8d2be-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="8d2be-119">Presuppone inoltre che il valore di target sia minore di $N $.</span><span class="sxs-lookup"><span data-stu-id="8d2be-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="8d2be-120">Per il diagramma di circuito e la spiegazione, vedere la figura 5 [della pagina 5 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="8d2be-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d2be-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d2be-121">See Also</span></span>

- [<span data-ttu-id="8d2be-122">Microsoft. Quantum. aritmetic. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8d2be-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)
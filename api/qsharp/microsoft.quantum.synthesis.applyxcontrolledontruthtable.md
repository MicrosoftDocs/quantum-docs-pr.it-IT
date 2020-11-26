---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operazione ApplyXControlledOnTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203298"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="bf8bb-102">Operazione ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="bf8bb-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="bf8bb-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="bf8bb-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="bf8bb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf8bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf8bb-105">Applica l' @"microsoft.quantum.intrinsic.x" operazione su `target` , se la funzione booleana `func` restituisce true per l'assegnazione classica in `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="bf8bb-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bf8bb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf8bb-106">Description</span></span>

<span data-ttu-id="bf8bb-107">L'operazione implementa l'operazione unitaria \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align} in cui $x $ e $y $ `controlRegister` rappresentano `target` rispettivamente e.</span><span class="sxs-lookup"><span data-stu-id="bf8bb-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="bf8bb-108">La funzione booleana $f $ viene rappresentata come una tabella di verità in termini di un valore Integer grande.</span><span class="sxs-lookup"><span data-stu-id="bf8bb-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="bf8bb-109">La funzione di maggioranza su tre input, ad esempio, è rappresentata da Bitstring `11101000` , dove il bit più significativo `1` corrisponde all'assegnazione di input `(1, 1, 1)` e il bit meno significativo `0` corrisponde all'assegnazione di input `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="bf8bb-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="bf8bb-110">Può essere rappresentata da un Big Integer `0xE8L` in notazione esadecimale o come `232L` notazione decimale.</span><span class="sxs-lookup"><span data-stu-id="bf8bb-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="bf8bb-111">Il `L` suffisso indica che la costante è di tipo `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="bf8bb-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="bf8bb-112">Altre informazioni su questa rappresentazione sono disponibili anche nella pagina relativa alla [verità Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="bf8bb-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="bf8bb-113">L'implementazione utilizza le attività di controllo @"microsoft.quantum.intrinsic.cnot" e @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="bf8bb-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="bf8bb-114">Input</span><span class="sxs-lookup"><span data-stu-id="bf8bb-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="bf8bb-115">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bf8bb-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bf8bb-116">Tabella di verità booleana rappresentata come valore Big Integer</span><span class="sxs-lookup"><span data-stu-id="bf8bb-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="bf8bb-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf8bb-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf8bb-118">Registro dei qubits di controllo</span><span class="sxs-lookup"><span data-stu-id="bf8bb-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bf8bb-119">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bf8bb-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bf8bb-120">Qubit di destinazione</span><span class="sxs-lookup"><span data-stu-id="bf8bb-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf8bb-121">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf8bb-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="bf8bb-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="bf8bb-122">References</span></span>

- [<span data-ttu-id="bf8bb-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: quanti-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="bf8bb-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="bf8bb-124">*Mathias Soeken*, *Martin Roetteler*, arXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="bf8bb-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="bf8bb-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf8bb-125">See Also</span></span>

- [<span data-ttu-id="bf8bb-126">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="bf8bb-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)
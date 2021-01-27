---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Operazione ApplyInnerTTKAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843823"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="e5e54-102">Operazione ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="e5e54-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="e5e54-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e5e54-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e5e54-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5e54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5e54-105">Implementa la funzione di addizione interna per l'operazione RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e5e54-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="e5e54-106">Si tratta dell'operazione interna che viene coniugata con l'operazione esterna per costruire il Adder completo.</span><span class="sxs-lookup"><span data-stu-id="e5e54-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e5e54-107">Input</span><span class="sxs-lookup"><span data-stu-id="e5e54-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e5e54-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5e54-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e5e54-109">LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e5e54-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e5e54-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5e54-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e5e54-111">LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e5e54-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="e5e54-112">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5e54-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5e54-113">Carry qubit, is XORed con il bit più significativo della somma.</span><span class="sxs-lookup"><span data-stu-id="e5e54-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5e54-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5e54-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e5e54-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="e5e54-115">Remarks</span></span>

<span data-ttu-id="e5e54-116">L'operazione controllata specificata si avvale della simmetria e dell'annullamento reciproco delle operazioni per migliorare l'implementazione predefinita che aggiunge un controllo a ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="e5e54-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="e5e54-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e5e54-117">References</span></span>

- <span data-ttu-id="e5e54-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="e5e54-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530
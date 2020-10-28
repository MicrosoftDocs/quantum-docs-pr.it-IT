---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Operazione ApplyInnerTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721659"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="aad74-102">Operazione ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="aad74-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="aad74-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aad74-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aad74-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aad74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aad74-105">Implementa la funzione di addizione interna per l'operazione RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="aad74-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="aad74-106">Si tratta dell'operazione interna che viene coniugata con l'operazione esterna per costruire il Adder completo.</span><span class="sxs-lookup"><span data-stu-id="aad74-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="aad74-107">Input</span><span class="sxs-lookup"><span data-stu-id="aad74-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="aad74-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aad74-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aad74-109">LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="aad74-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="aad74-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aad74-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aad74-111">LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="aad74-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="aad74-112">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aad74-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aad74-113">Carry qubit, is XORed con il bit più significativo della somma.</span><span class="sxs-lookup"><span data-stu-id="aad74-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aad74-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aad74-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aad74-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="aad74-115">Remarks</span></span>

<span data-ttu-id="aad74-116">L'operazione controllata specificata si avvale della simmetria e dell'annullamento reciproco delle operazioni per migliorare l'implementazione predefinita che aggiunge un controllo a ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="aad74-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="aad74-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="aad74-117">References</span></span>

- <span data-ttu-id="aad74-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="aad74-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530
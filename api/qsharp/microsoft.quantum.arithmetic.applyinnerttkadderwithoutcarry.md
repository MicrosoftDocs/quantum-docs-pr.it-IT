---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Operazione ApplyInnerTTKAdderWithoutCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 0c1626c788215181b5ed45dc98bed928b5e4848a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843817"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="ed770-102">Operazione ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="ed770-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="ed770-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ed770-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ed770-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed770-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed770-105">Implementa la funzione di addizione interna per l'operazione RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed770-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="ed770-106">Si tratta dell'operazione interna che viene coniugata con l'operazione esterna per costruire il Adder completo.</span><span class="sxs-lookup"><span data-stu-id="ed770-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ed770-107">Input</span><span class="sxs-lookup"><span data-stu-id="ed770-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ed770-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ed770-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ed770-109">LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed770-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ed770-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ed770-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ed770-111">LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed770-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed770-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed770-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ed770-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="ed770-113">Remarks</span></span>

<span data-ttu-id="ed770-114">L'operazione controllata specificata si avvale della simmetria e dell'annullamento reciproco delle operazioni per migliorare l'implementazione predefinita che aggiunge un controllo a ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="ed770-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="ed770-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ed770-115">References</span></span>

- <span data-ttu-id="ed770-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="ed770-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530
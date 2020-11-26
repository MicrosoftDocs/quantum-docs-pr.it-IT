---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operazione ApplyOuterTTKAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190616"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="f1d19-102">Operazione ApplyOuterTTKAdder</span><span class="sxs-lookup"><span data-stu-id="f1d19-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="f1d19-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f1d19-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f1d19-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1d19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1d19-105">Implementa l'operazione esterna per RippleCarryAdderTTK per coniugare l'operazione interna per costruire la vipera completa.</span><span class="sxs-lookup"><span data-stu-id="f1d19-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f1d19-106">Input</span><span class="sxs-lookup"><span data-stu-id="f1d19-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f1d19-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1d19-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f1d19-108">LittleEndian qubit registra la codifica del primo input summand Integer in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="f1d19-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f1d19-109">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1d19-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f1d19-110">LittleEndian qubit Register che codifica il secondo Integer summand input in RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="f1d19-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1d19-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1d19-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f1d19-112">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f1d19-112">References</span></span>

- <span data-ttu-id="f1d19-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="f1d19-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530
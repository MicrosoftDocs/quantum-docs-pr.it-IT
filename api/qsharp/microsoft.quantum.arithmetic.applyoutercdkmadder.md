---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operazione ApplyOuterCDKMAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721566"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="f9457-102">Operazione ApplyOuterCDKMAdder</span><span class="sxs-lookup"><span data-stu-id="f9457-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="f9457-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f9457-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f9457-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9457-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9457-105">Operazione di ripple sul posto reversibile utilizzata nell'operazione di addizione Integer RippleCarryAdderCDKM di seguito.</span><span class="sxs-lookup"><span data-stu-id="f9457-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="f9457-106">Dato due registri qubit `xs` e `ys` della stessa lunghezza, l'operazione applica una sequenza di trascinamento delle Ripple di CNOT e CCNOT Gates con qubits in `xs` e `ys` come controlli e qubits in `xs` come destinazioni.</span><span class="sxs-lookup"><span data-stu-id="f9457-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f9457-107">Input</span><span class="sxs-lookup"><span data-stu-id="f9457-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f9457-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9457-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9457-109">Primo registro qubit, che contiene i controlli e le destinazioni.</span><span class="sxs-lookup"><span data-stu-id="f9457-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f9457-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9457-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9457-111">Secondo registro qubit, che contribuisce ai controlli.</span><span class="sxs-lookup"><span data-stu-id="f9457-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="f9457-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9457-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9457-113">Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f9457-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9457-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9457-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f9457-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f9457-115">References</span></span>

- <span data-ttu-id="f9457-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="f9457-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1
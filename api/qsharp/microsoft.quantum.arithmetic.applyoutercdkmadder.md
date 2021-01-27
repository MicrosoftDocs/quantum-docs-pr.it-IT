---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operazione ApplyOuterCDKMAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843715"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="94487-102">Operazione ApplyOuterCDKMAdder</span><span class="sxs-lookup"><span data-stu-id="94487-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="94487-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="94487-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="94487-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94487-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94487-105">Operazione di ripple sul posto reversibile utilizzata nell'operazione di addizione Integer RippleCarryAdderCDKM di seguito.</span><span class="sxs-lookup"><span data-stu-id="94487-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="94487-106">Dato due registri qubit `xs` e `ys` della stessa lunghezza, l'operazione applica una sequenza di trascinamento delle Ripple di CNOT e CCNOT Gates con qubits in `xs` e `ys` come controlli e qubits in `xs` come destinazioni.</span><span class="sxs-lookup"><span data-stu-id="94487-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="94487-107">Input</span><span class="sxs-lookup"><span data-stu-id="94487-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="94487-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="94487-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="94487-109">Primo registro qubit, che contiene i controlli e le destinazioni.</span><span class="sxs-lookup"><span data-stu-id="94487-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="94487-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="94487-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="94487-111">Secondo registro qubit, che contribuisce ai controlli.</span><span class="sxs-lookup"><span data-stu-id="94487-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="94487-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94487-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94487-113">Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.</span><span class="sxs-lookup"><span data-stu-id="94487-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94487-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94487-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="94487-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="94487-115">References</span></span>

- <span data-ttu-id="94487-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="94487-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1
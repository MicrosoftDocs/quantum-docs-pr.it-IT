---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operazione ApplyToSubregisterC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2a2eb7ee5b437ec5fb633bfb4bdccd0cb1d253ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208024"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="80405-102">Operazione ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="80405-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="80405-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80405-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80405-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80405-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80405-105">Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.</span><span class="sxs-lookup"><span data-stu-id="80405-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="80405-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="80405-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="80405-107">Input</span><span class="sxs-lookup"><span data-stu-id="80405-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="80405-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="80405-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="80405-109">Operazione da applicare al sottoregistro.</span><span class="sxs-lookup"><span data-stu-id="80405-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="80405-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="80405-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="80405-111">Matrice di indici, che indica a quale qubits verrà applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="80405-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="80405-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="80405-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="80405-113">Registro in cui viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="80405-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80405-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80405-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="80405-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80405-115">See Also</span></span>

- [<span data-ttu-id="80405-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="80405-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
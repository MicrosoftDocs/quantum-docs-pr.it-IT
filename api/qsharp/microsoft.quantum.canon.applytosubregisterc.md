---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operazione ApplyToSubregisterC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717002"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="381c8-102">Operazione ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="381c8-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="381c8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="381c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="381c8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="381c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="381c8-105">Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.</span><span class="sxs-lookup"><span data-stu-id="381c8-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="381c8-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="381c8-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="381c8-107">Input</span><span class="sxs-lookup"><span data-stu-id="381c8-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="381c8-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="381c8-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="381c8-109">Operazione da applicare al sottoregistro.</span><span class="sxs-lookup"><span data-stu-id="381c8-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="381c8-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="381c8-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="381c8-111">Matrice di indici, che indica a quale qubits verrà applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="381c8-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="381c8-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="381c8-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="381c8-113">Registro in cui viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="381c8-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="381c8-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="381c8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="381c8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="381c8-115">See Also</span></span>

- [<span data-ttu-id="381c8-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="381c8-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
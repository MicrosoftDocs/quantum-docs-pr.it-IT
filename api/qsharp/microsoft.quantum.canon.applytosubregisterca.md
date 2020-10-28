---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Operazione ApplyToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716988"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="c00eb-102">Operazione ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="c00eb-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="c00eb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c00eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c00eb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c00eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c00eb-105">Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.</span><span class="sxs-lookup"><span data-stu-id="c00eb-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="c00eb-106">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="c00eb-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c00eb-107">Input</span><span class="sxs-lookup"><span data-stu-id="c00eb-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="c00eb-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="c00eb-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="c00eb-109">Operazione da applicare al sottoregistro.</span><span class="sxs-lookup"><span data-stu-id="c00eb-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="c00eb-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c00eb-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c00eb-111">Matrice di indici, che indica a quale qubits verrà applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c00eb-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c00eb-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c00eb-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c00eb-113">Registro in cui viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c00eb-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c00eb-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c00eb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c00eb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c00eb-115">See Also</span></span>

- [<span data-ttu-id="c00eb-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="c00eb-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
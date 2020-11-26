---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Operazione ApplyToSubregisterA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: edea0e565984cffb13b146cb336f90762f647636
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208058"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="8ff0f-102">Operazione ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="8ff0f-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="8ff0f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ff0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ff0f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ff0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ff0f-105">Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="8ff0f-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="8ff0f-107">Input</span><span class="sxs-lookup"><span data-stu-id="8ff0f-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="8ff0f-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="8ff0f-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8ff0f-109">Operazione da applicare al sottoregistro.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8ff0f-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8ff0f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8ff0f-111">Matrice di indici, che indica a quale qubits verrà applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8ff0f-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8ff0f-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8ff0f-113">Registro in cui viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ff0f-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ff0f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8ff0f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff0f-115">See Also</span></span>

- [<span data-ttu-id="8ff0f-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="8ff0f-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
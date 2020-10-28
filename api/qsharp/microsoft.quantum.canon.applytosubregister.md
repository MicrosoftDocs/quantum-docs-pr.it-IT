---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operazione ApplyToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717030"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="a051b-102">Operazione ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="a051b-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="a051b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a051b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a051b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a051b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a051b-105">Applica un'operazione a un sottoregistro di un registro, con qubits specificato da una matrice di indici.</span><span class="sxs-lookup"><span data-stu-id="a051b-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a051b-106">Input</span><span class="sxs-lookup"><span data-stu-id="a051b-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="a051b-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a051b-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a051b-108">Operazione da applicare al sottoregistro.</span><span class="sxs-lookup"><span data-stu-id="a051b-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="a051b-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a051b-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a051b-110">Matrice di indici, che indica a quale qubits verrà applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a051b-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a051b-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a051b-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a051b-112">Registro in cui viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a051b-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a051b-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a051b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a051b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a051b-114">See Also</span></span>

- [<span data-ttu-id="a051b-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="a051b-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="a051b-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="a051b-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="a051b-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="a051b-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)
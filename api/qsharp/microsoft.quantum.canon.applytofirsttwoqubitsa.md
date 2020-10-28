---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Operazione ApplyToFirstTwoQubitsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717307"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="fff8f-102">Operazione ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="fff8f-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="fff8f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fff8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fff8f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fff8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fff8f-105">Applica un'operazione ai primi due qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="fff8f-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="fff8f-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="fff8f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fff8f-107">Input</span><span class="sxs-lookup"><span data-stu-id="fff8f-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="fff8f-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="fff8f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fff8f-109">Operazione da applicare ai primi due qubits</span><span class="sxs-lookup"><span data-stu-id="fff8f-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fff8f-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fff8f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fff8f-111">Matrice qubit per i primi due qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fff8f-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fff8f-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fff8f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fff8f-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="fff8f-113">Remarks</span></span>

<span data-ttu-id="fff8f-114">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="fff8f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="fff8f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fff8f-115">See Also</span></span>

- [<span data-ttu-id="fff8f-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="fff8f-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
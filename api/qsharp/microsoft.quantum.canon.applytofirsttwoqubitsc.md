---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operazione ApplyToFirstTwoQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717282"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="df88a-102">Operazione ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="df88a-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="df88a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df88a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df88a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df88a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df88a-105">Applica un'operazione ai primi due qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="df88a-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="df88a-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="df88a-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="df88a-107">Input</span><span class="sxs-lookup"><span data-stu-id="df88a-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="df88a-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="df88a-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="df88a-109">Operazione da applicare ai primi due qubits</span><span class="sxs-lookup"><span data-stu-id="df88a-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="df88a-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df88a-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df88a-111">Matrice qubit per i primi due qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="df88a-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df88a-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df88a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="df88a-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="df88a-113">Remarks</span></span>

<span data-ttu-id="df88a-114">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="df88a-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="df88a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df88a-115">See Also</span></span>

- [<span data-ttu-id="df88a-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="df88a-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
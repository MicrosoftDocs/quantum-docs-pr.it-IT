---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operazione ApplyToFirstThreeQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717377"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="d04cd-102">Operazione ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="d04cd-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="d04cd-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d04cd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d04cd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d04cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d04cd-105">Applica un'operazione ai primi tre qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="d04cd-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="d04cd-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="d04cd-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d04cd-107">Input</span><span class="sxs-lookup"><span data-stu-id="d04cd-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="d04cd-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="d04cd-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d04cd-109">Operazione da applicare ai primi tre qubits</span><span class="sxs-lookup"><span data-stu-id="d04cd-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d04cd-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d04cd-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d04cd-111">Matrice qubit per le prime tre qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d04cd-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d04cd-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d04cd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d04cd-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="d04cd-113">Remarks</span></span>

<span data-ttu-id="d04cd-114">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="d04cd-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="d04cd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d04cd-115">See Also</span></span>

- [<span data-ttu-id="d04cd-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="d04cd-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)
---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operazione ApplyToFirstThreeQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717380"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="3f939-102">Operazione ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="3f939-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="3f939-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3f939-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3f939-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f939-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f939-105">Applica un'operazione ai primi tre qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="3f939-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f939-106">Input</span><span class="sxs-lookup"><span data-stu-id="3f939-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="3f939-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3f939-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3f939-108">Operazione da applicare ai primi tre qubits</span><span class="sxs-lookup"><span data-stu-id="3f939-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3f939-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f939-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f939-110">Matrice qubit per le prime tre qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3f939-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f939-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f939-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3f939-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="3f939-112">Remarks</span></span>

<span data-ttu-id="3f939-113">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="3f939-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="3f939-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f939-114">See Also</span></span>

- [<span data-ttu-id="3f939-115">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="3f939-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="3f939-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="3f939-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="3f939-117">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="3f939-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)
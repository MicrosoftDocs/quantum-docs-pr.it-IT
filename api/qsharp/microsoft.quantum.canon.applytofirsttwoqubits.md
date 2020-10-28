---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Operazione ApplyToFirstTwoQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717310"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="f1e82-102">Operazione ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="f1e82-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="f1e82-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1e82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1e82-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1e82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1e82-105">Applica un'operazione ai primi due qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="f1e82-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f1e82-106">Input</span><span class="sxs-lookup"><span data-stu-id="f1e82-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="f1e82-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f1e82-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f1e82-108">Operazione da applicare ai primi due qubits</span><span class="sxs-lookup"><span data-stu-id="f1e82-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f1e82-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1e82-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1e82-110">Matrice qubit per i primi due qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f1e82-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1e82-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1e82-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f1e82-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="f1e82-112">Remarks</span></span>

<span data-ttu-id="f1e82-113">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="f1e82-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="f1e82-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1e82-114">See Also</span></span>

- [<span data-ttu-id="f1e82-115">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="f1e82-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="f1e82-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="f1e82-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="f1e82-117">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="f1e82-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)
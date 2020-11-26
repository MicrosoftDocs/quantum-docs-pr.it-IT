---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operazione ApplyToFirstQubitCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bc2b1275b4258b9cc2db45c9e5cfe14f7eee0c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208806"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="2dcd1-102">Operazione ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="2dcd1-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="2dcd1-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2dcd1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2dcd1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2dcd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2dcd1-105">Applica Operation op al primo qubit nel registro.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="2dcd1-106">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2dcd1-107">Input</span><span class="sxs-lookup"><span data-stu-id="2dcd1-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2dcd1-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) qubit è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2dcd1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2dcd1-109">Operazione da applicare al primo qubit</span><span class="sxs-lookup"><span data-stu-id="2dcd1-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="2dcd1-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2dcd1-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2dcd1-111">Matrice qubit per la prima qubit di cui viene applicata l'operazione</span><span class="sxs-lookup"><span data-stu-id="2dcd1-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dcd1-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dcd1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2dcd1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dcd1-113">See Also</span></span>

- [<span data-ttu-id="2dcd1-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="2dcd1-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
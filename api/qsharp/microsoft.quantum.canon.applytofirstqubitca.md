---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operazione ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717394"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="2492a-102">Operazione ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="2492a-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="2492a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2492a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2492a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2492a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2492a-105">Applica Operation op al primo qubit nel registro.</span><span class="sxs-lookup"><span data-stu-id="2492a-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="2492a-106">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="2492a-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2492a-107">Input</span><span class="sxs-lookup"><span data-stu-id="2492a-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="2492a-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) di registrazione e CTL</span><span class="sxs-lookup"><span data-stu-id="2492a-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2492a-109">Operazione da applicare al primo qubit</span><span class="sxs-lookup"><span data-stu-id="2492a-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="2492a-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2492a-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2492a-111">Matrice qubit per la prima qubit di cui viene applicata l'operazione</span><span class="sxs-lookup"><span data-stu-id="2492a-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="2492a-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2492a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2492a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2492a-113">See Also</span></span>

- [<span data-ttu-id="2492a-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="2492a-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
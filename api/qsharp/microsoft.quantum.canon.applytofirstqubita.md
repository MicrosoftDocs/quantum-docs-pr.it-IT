---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operazione ApplyToFirstQubitA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717405"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="7c168-102">Operazione ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="7c168-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="7c168-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c168-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c168-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c168-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c168-105">Applica un'operazione al primo qubit nel registro.</span><span class="sxs-lookup"><span data-stu-id="7c168-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="7c168-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="7c168-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7c168-107">Input</span><span class="sxs-lookup"><span data-stu-id="7c168-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="7c168-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="7c168-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c168-109">Operazione da applicare al primo qubit</span><span class="sxs-lookup"><span data-stu-id="7c168-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="7c168-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7c168-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7c168-111">Matrice qubit per la prima qubit di cui viene applicata l'operazione</span><span class="sxs-lookup"><span data-stu-id="7c168-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c168-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c168-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7c168-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c168-113">See Also</span></span>

- [<span data-ttu-id="7c168-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="7c168-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
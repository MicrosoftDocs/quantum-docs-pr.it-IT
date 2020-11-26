---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operazione ApplyToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208840"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="bbabc-102">Operazione ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="bbabc-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="bbabc-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bbabc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bbabc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bbabc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bbabc-105">Applica un'operazione al primo qubit nel registro.</span><span class="sxs-lookup"><span data-stu-id="bbabc-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="bbabc-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="bbabc-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bbabc-107">Input</span><span class="sxs-lookup"><span data-stu-id="bbabc-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="bbabc-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) l' => [unità](xref:microsoft.quantum.lang-ref.unit) qubit è ADJ</span><span class="sxs-lookup"><span data-stu-id="bbabc-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bbabc-109">Operazione da applicare al primo qubit</span><span class="sxs-lookup"><span data-stu-id="bbabc-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="bbabc-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bbabc-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bbabc-111">Matrice qubit per la prima qubit di cui viene applicata l'operazione</span><span class="sxs-lookup"><span data-stu-id="bbabc-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbabc-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbabc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bbabc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbabc-113">See Also</span></span>

- [<span data-ttu-id="bbabc-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="bbabc-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
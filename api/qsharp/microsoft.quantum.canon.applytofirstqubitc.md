---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operazione ApplyToFirstQubitC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a36d20e03ebed82435d1d4136f4ce777eb468926
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850708"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="6f94e-102">Operazione ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="6f94e-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="6f94e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f94e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f94e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f94e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f94e-105">Applica Operation op al primo qubit nel registro.</span><span class="sxs-lookup"><span data-stu-id="6f94e-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="6f94e-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="6f94e-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="6f94e-107">Input</span><span class="sxs-lookup"><span data-stu-id="6f94e-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="6f94e-108">op: [](xref:microsoft.quantum.lang-ref.qubit) l' => [unità](xref:microsoft.quantum.lang-ref.unit) qubit è CTL</span><span class="sxs-lookup"><span data-stu-id="6f94e-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6f94e-109">Operazione da applicare al primo qubit</span><span class="sxs-lookup"><span data-stu-id="6f94e-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6f94e-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6f94e-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6f94e-111">Matrice qubit per la prima qubit di cui viene applicata l'operazione</span><span class="sxs-lookup"><span data-stu-id="6f94e-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f94e-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f94e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6f94e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f94e-113">See Also</span></span>

- [<span data-ttu-id="6f94e-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="6f94e-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)
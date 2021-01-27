---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operazione ApplyToEachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850845"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="61453-102">Operazione ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="61453-102">ApplyToEachC operation</span></span>

<span data-ttu-id="61453-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61453-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61453-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61453-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61453-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="61453-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="61453-106">Il modificatore `C` indica che l'operazione Single-qubit è controllabile.</span><span class="sxs-lookup"><span data-stu-id="61453-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="61453-107">Input</span><span class="sxs-lookup"><span data-stu-id="61453-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="61453-108">singleElementOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="61453-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61453-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="61453-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="61453-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="61453-110">register : 'T[]</span></span>

<span data-ttu-id="61453-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="61453-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61453-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61453-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61453-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="61453-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61453-114">T</span><span class="sxs-lookup"><span data-stu-id="61453-114">'T</span></span>

<span data-ttu-id="61453-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="61453-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="61453-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="61453-116">Example</span></span>

<span data-ttu-id="61453-117">Preparare uno stato di tre qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="61453-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="61453-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61453-118">See Also</span></span>

- [<span data-ttu-id="61453-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="61453-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
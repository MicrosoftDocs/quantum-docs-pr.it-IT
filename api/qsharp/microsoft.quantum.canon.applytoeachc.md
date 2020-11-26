---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operazione ApplyToEachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217782"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="b7c59-102">Operazione ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="b7c59-102">ApplyToEachC operation</span></span>

<span data-ttu-id="b7c59-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7c59-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7c59-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7c59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7c59-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="b7c59-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="b7c59-106">Il modificatore `C` indica che l'operazione Single-qubit è controllabile.</span><span class="sxs-lookup"><span data-stu-id="b7c59-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="b7c59-107">Input</span><span class="sxs-lookup"><span data-stu-id="b7c59-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="b7c59-108">singleElementOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="b7c59-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b7c59-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="b7c59-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="b7c59-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="b7c59-110">register : 'T[]</span></span>

<span data-ttu-id="b7c59-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="b7c59-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7c59-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7c59-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b7c59-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b7c59-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7c59-114">T</span><span class="sxs-lookup"><span data-stu-id="b7c59-114">'T</span></span>

<span data-ttu-id="b7c59-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b7c59-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7c59-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7c59-116">See Also</span></span>

- [<span data-ttu-id="b7c59-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="b7c59-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
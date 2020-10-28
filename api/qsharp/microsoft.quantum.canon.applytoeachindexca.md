---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operazione ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717517"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="c505d-102">Operazione ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="c505d-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="c505d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c505d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c505d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c505d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c505d-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="c505d-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="c505d-106">Il modificatore `CA` indica che l'operazione Single-qubit è adjointable e controllabile.</span><span class="sxs-lookup"><span data-stu-id="c505d-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c505d-107">Input</span><span class="sxs-lookup"><span data-stu-id="c505d-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="c505d-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c505d-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c505d-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="c505d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c505d-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="c505d-110">register : 'T[]</span></span>

<span data-ttu-id="c505d-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="c505d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c505d-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c505d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c505d-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c505d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c505d-114">T</span><span class="sxs-lookup"><span data-stu-id="c505d-114">'T</span></span>

<span data-ttu-id="c505d-115">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="c505d-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="c505d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c505d-116">See Also</span></span>

- [<span data-ttu-id="c505d-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="c505d-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
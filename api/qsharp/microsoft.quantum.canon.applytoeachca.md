---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operazione ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717548"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="afdec-102">Operazione ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="afdec-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="afdec-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="afdec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="afdec-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afdec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afdec-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="afdec-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="afdec-106">Il modificatore `CA` indica che l'operazione Single-qubit è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="afdec-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="afdec-107">Input</span><span class="sxs-lookup"><span data-stu-id="afdec-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="afdec-108">singleElementOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="afdec-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="afdec-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="afdec-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="afdec-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="afdec-110">register : 'T[]</span></span>

<span data-ttu-id="afdec-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="afdec-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afdec-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afdec-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="afdec-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="afdec-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afdec-114">T</span><span class="sxs-lookup"><span data-stu-id="afdec-114">'T</span></span>

<span data-ttu-id="afdec-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="afdec-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="afdec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afdec-116">See Also</span></span>

- [<span data-ttu-id="afdec-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="afdec-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
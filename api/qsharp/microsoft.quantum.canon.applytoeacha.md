---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Operazione ApplyToEachA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717576"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="fafaa-102">Operazione ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="fafaa-102">ApplyToEachA operation</span></span>

<span data-ttu-id="fafaa-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fafaa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fafaa-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fafaa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fafaa-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="fafaa-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="fafaa-106">Il modificatore `A` indica che l'operazione Single-qubit è adjointable.</span><span class="sxs-lookup"><span data-stu-id="fafaa-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fafaa-107">Input</span><span class="sxs-lookup"><span data-stu-id="fafaa-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="fafaa-108">singleElementOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fafaa-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fafaa-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="fafaa-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="fafaa-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="fafaa-110">register : 'T[]</span></span>

<span data-ttu-id="fafaa-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="fafaa-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fafaa-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fafaa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fafaa-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="fafaa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fafaa-114">T</span><span class="sxs-lookup"><span data-stu-id="fafaa-114">'T</span></span>

<span data-ttu-id="fafaa-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fafaa-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="fafaa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fafaa-116">See Also</span></span>

- [<span data-ttu-id="fafaa-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="fafaa-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
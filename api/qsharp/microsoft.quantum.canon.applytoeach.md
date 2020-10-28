---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operazione ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717590"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="3efc0-102">Operazione ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="3efc0-102">ApplyToEach operation</span></span>

<span data-ttu-id="3efc0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3efc0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3efc0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3efc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3efc0-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="3efc0-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3efc0-106">Input</span><span class="sxs-lookup"><span data-stu-id="3efc0-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="3efc0-107">singleElementOperation:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3efc0-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3efc0-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="3efc0-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3efc0-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="3efc0-109">register : 'T[]</span></span>

<span data-ttu-id="3efc0-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3efc0-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3efc0-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3efc0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3efc0-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3efc0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3efc0-113">T</span><span class="sxs-lookup"><span data-stu-id="3efc0-113">'T</span></span>

<span data-ttu-id="3efc0-114">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3efc0-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3efc0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3efc0-115">See Also</span></span>

- [<span data-ttu-id="3efc0-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="3efc0-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="3efc0-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="3efc0-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="3efc0-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="3efc0-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operazione ApplyToEachIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717545"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="91519-102">Operazione ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="91519-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="91519-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91519-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91519-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91519-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91519-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="91519-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="91519-106">Input</span><span class="sxs-lookup"><span data-stu-id="91519-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="91519-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="91519-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="91519-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="91519-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="91519-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="91519-109">register : 'T[]</span></span>

<span data-ttu-id="91519-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="91519-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91519-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91519-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="91519-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="91519-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91519-113">T</span><span class="sxs-lookup"><span data-stu-id="91519-113">'T</span></span>

<span data-ttu-id="91519-114">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="91519-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="91519-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91519-115">See Also</span></span>

- [<span data-ttu-id="91519-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="91519-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="91519-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="91519-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="91519-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="91519-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="91519-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="91519-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)
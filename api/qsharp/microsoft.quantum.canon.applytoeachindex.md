---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operazione ApplyToEachIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217613"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="9e0b8-102">Operazione ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="9e0b8-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="9e0b8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e0b8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e0b8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e0b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e0b8-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="9e0b8-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9e0b8-106">Input</span><span class="sxs-lookup"><span data-stu-id="9e0b8-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="9e0b8-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9e0b8-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9e0b8-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="9e0b8-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9e0b8-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="9e0b8-109">register : 'T[]</span></span>

<span data-ttu-id="9e0b8-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="9e0b8-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e0b8-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e0b8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9e0b8-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9e0b8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e0b8-113">T</span><span class="sxs-lookup"><span data-stu-id="9e0b8-113">'T</span></span>

<span data-ttu-id="9e0b8-114">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="9e0b8-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e0b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e0b8-115">See Also</span></span>

- [<span data-ttu-id="9e0b8-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="9e0b8-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="9e0b8-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="9e0b8-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="9e0b8-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="9e0b8-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="9e0b8-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="9e0b8-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)
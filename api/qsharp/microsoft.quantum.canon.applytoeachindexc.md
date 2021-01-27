---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operazione ApplyToEachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850813"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="d8d69-102">Operazione ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="d8d69-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="d8d69-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8d69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8d69-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8d69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8d69-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="d8d69-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="d8d69-106">Il modificatore `C` indica che l'operazione Single-qubit è controllabile.</span><span class="sxs-lookup"><span data-stu-id="d8d69-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d8d69-107">Input</span><span class="sxs-lookup"><span data-stu-id="d8d69-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="d8d69-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="d8d69-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d8d69-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="d8d69-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d8d69-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="d8d69-110">register : 'T[]</span></span>

<span data-ttu-id="d8d69-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="d8d69-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8d69-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8d69-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d8d69-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d8d69-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8d69-114">T</span><span class="sxs-lookup"><span data-stu-id="d8d69-114">'T</span></span>

<span data-ttu-id="d8d69-115">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d8d69-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8d69-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d69-116">See Also</span></span>

- [<span data-ttu-id="d8d69-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="d8d69-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
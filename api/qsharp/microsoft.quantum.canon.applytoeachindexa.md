---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operazione ApplyToEachIndexA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717534"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="675b5-102">Operazione ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="675b5-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="675b5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="675b5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="675b5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="675b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="675b5-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="675b5-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="675b5-106">Il modificatore `A` indica che l'operazione Single-qubit è adjointable.</span><span class="sxs-lookup"><span data-stu-id="675b5-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="675b5-107">Input</span><span class="sxs-lookup"><span data-stu-id="675b5-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="675b5-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="675b5-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="675b5-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="675b5-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="675b5-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="675b5-110">register : 'T[]</span></span>

<span data-ttu-id="675b5-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="675b5-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="675b5-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="675b5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="675b5-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="675b5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="675b5-114">T</span><span class="sxs-lookup"><span data-stu-id="675b5-114">'T</span></span>

<span data-ttu-id="675b5-115">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="675b5-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="675b5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="675b5-116">See Also</span></span>

- [<span data-ttu-id="675b5-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="675b5-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
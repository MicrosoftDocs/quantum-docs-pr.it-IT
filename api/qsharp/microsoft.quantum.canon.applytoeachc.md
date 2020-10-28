---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operazione ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717562"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="9b029-102">Operazione ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="9b029-102">ApplyToEachC operation</span></span>

<span data-ttu-id="9b029-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b029-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b029-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b029-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b029-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="9b029-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="9b029-106">Il modificatore `C` indica che l'operazione Single-qubit è controllabile.</span><span class="sxs-lookup"><span data-stu-id="9b029-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9b029-107">Input</span><span class="sxs-lookup"><span data-stu-id="9b029-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="9b029-108">singleElementOperation:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b029-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9b029-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="9b029-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9b029-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="9b029-110">register : 'T[]</span></span>

<span data-ttu-id="9b029-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="9b029-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b029-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b029-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b029-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9b029-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b029-114">T</span><span class="sxs-lookup"><span data-stu-id="9b029-114">'T</span></span>

<span data-ttu-id="9b029-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="9b029-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b029-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b029-116">See Also</span></span>

- [<span data-ttu-id="9b029-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="9b029-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
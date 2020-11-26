---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operazione ApplyToEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217867"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="ba86e-102">Operazione ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="ba86e-102">ApplyToEach operation</span></span>

<span data-ttu-id="ba86e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba86e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba86e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba86e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba86e-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="ba86e-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ba86e-106">Input</span><span class="sxs-lookup"><span data-stu-id="ba86e-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="ba86e-107">singleElementOperation:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ba86e-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ba86e-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="ba86e-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ba86e-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="ba86e-109">register : 'T[]</span></span>

<span data-ttu-id="ba86e-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="ba86e-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba86e-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba86e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ba86e-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="ba86e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba86e-113">T</span><span class="sxs-lookup"><span data-stu-id="ba86e-113">'T</span></span>

<span data-ttu-id="ba86e-114">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ba86e-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba86e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba86e-115">See Also</span></span>

- [<span data-ttu-id="ba86e-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ba86e-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="ba86e-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="ba86e-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="ba86e-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="ba86e-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
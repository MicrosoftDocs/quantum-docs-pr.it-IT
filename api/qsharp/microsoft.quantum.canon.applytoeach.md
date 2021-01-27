---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operazione ApplyToEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844632"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="15198-102">Operazione ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="15198-102">ApplyToEach operation</span></span>

<span data-ttu-id="15198-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15198-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15198-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15198-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15198-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="15198-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="15198-106">Input</span><span class="sxs-lookup"><span data-stu-id="15198-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="15198-107">singleElementOperation:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="15198-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="15198-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="15198-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="15198-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="15198-109">register : 'T[]</span></span>

<span data-ttu-id="15198-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="15198-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15198-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15198-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15198-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="15198-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15198-113">T</span><span class="sxs-lookup"><span data-stu-id="15198-113">'T</span></span>

<span data-ttu-id="15198-114">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="15198-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="15198-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="15198-115">Example</span></span>

<span data-ttu-id="15198-116">Preparare uno stato di tre qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="15198-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="15198-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15198-117">See Also</span></span>

- [<span data-ttu-id="15198-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="15198-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="15198-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="15198-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="15198-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="15198-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
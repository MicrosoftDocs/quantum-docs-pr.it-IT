---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Operazione ApplyToEachA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217799"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="17873-102">Operazione ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="17873-102">ApplyToEachA operation</span></span>

<span data-ttu-id="17873-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17873-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17873-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17873-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17873-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="17873-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="17873-106">Il modificatore `A` indica che l'operazione Single-qubit è adjointable.</span><span class="sxs-lookup"><span data-stu-id="17873-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="17873-107">Input</span><span class="sxs-lookup"><span data-stu-id="17873-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="17873-108">singleElementOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="17873-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="17873-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="17873-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="17873-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="17873-110">register : 'T[]</span></span>

<span data-ttu-id="17873-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="17873-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17873-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17873-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17873-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="17873-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17873-114">T</span><span class="sxs-lookup"><span data-stu-id="17873-114">'T</span></span>

<span data-ttu-id="17873-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="17873-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="17873-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17873-116">See Also</span></span>

- [<span data-ttu-id="17873-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="17873-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
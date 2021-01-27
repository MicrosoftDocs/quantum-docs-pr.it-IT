---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operazione ApplyToEachCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841480"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="404e4-102">Operazione ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="404e4-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="404e4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="404e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="404e4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="404e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="404e4-105">Applica un'operazione Single-qubit a ogni elemento in un registro.</span><span class="sxs-lookup"><span data-stu-id="404e4-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="404e4-106">Il modificatore `CA` indica che l'operazione Single-qubit è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="404e4-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="404e4-107">Input</span><span class="sxs-lookup"><span data-stu-id="404e4-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="404e4-108">singleElementOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="404e4-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="404e4-109">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="404e4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="404e4-110">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="404e4-110">register : 'T[]</span></span>

<span data-ttu-id="404e4-111">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="404e4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="404e4-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="404e4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="404e4-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="404e4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="404e4-114">T</span><span class="sxs-lookup"><span data-stu-id="404e4-114">'T</span></span>

<span data-ttu-id="404e4-115">Destinazione su cui agisce l'operazione.</span><span class="sxs-lookup"><span data-stu-id="404e4-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="404e4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="404e4-116">Example</span></span>

<span data-ttu-id="404e4-117">Preparare uno stato di tre qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="404e4-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="404e4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="404e4-118">See Also</span></span>

- [<span data-ttu-id="404e4-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="404e4-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
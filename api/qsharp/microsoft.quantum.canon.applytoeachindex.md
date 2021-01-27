---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operazione ApplyToEachIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844601"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="66971-102">Operazione ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="66971-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="66971-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="66971-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="66971-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66971-105">Applica una singola operazione qubit a ogni elemento indicizzato in un registro.</span><span class="sxs-lookup"><span data-stu-id="66971-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="66971-106">Input</span><span class="sxs-lookup"><span data-stu-id="66971-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="66971-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int),' t) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="66971-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="66971-108">Operazione da applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="66971-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="66971-109">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="66971-109">register : 'T[]</span></span>

<span data-ttu-id="66971-110">Matrice di qubits su cui applicare l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="66971-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66971-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66971-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66971-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="66971-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66971-113">T</span><span class="sxs-lookup"><span data-stu-id="66971-113">'T</span></span>

<span data-ttu-id="66971-114">Destinazione in cui viene eseguita ciascuna operazione.</span><span class="sxs-lookup"><span data-stu-id="66971-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="66971-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66971-115">See Also</span></span>

- [<span data-ttu-id="66971-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="66971-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="66971-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="66971-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="66971-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="66971-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="66971-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="66971-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)
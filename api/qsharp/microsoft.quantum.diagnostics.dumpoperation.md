---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operazione DumpOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712858"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="55613-102">Operazione DumpOperation</span><span class="sxs-lookup"><span data-stu-id="55613-102">DumpOperation operation</span></span>

<span data-ttu-id="55613-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="55613-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="55613-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55613-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55613-105">Data un'operazione, Visualizza la diagnostica sull'operazione resa disponibile dalla destinazione di esecuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="55613-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="55613-106">Input</span><span class="sxs-lookup"><span data-stu-id="55613-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="55613-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55613-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55613-108">Numero di qubits su cui agisce l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="55613-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="55613-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55613-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="55613-110">Operazione da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="55613-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55613-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55613-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="55613-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="55613-112">Remarks</span></span>

<span data-ttu-id="55613-113">La chiamata a questa operazione non ha alcun effetto osservabile da Q #.</span><span class="sxs-lookup"><span data-stu-id="55613-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="55613-114">La diagnostica esatta visualizzata, se presente, dipende dalla destinazione di esecuzione corrente e dall'ambiente dell'editor.</span><span class="sxs-lookup"><span data-stu-id="55613-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="55613-115">Ad esempio, se usato nel simulatore Quantum a stato completo, viene visualizzata una matrice unitaria usata per rappresentare `op` .</span><span class="sxs-lookup"><span data-stu-id="55613-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="55613-116">Si noti che, quando vengono eseguiti su simulatori che ammettono un'ambiguità di una fase globale (ad esempio, il simulatore di stato completo), le rappresentazioni restituite possono variare fino a una fase globale.</span><span class="sxs-lookup"><span data-stu-id="55613-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="55613-117">Analogamente, l'ordine delle rappresentazioni di righe e colonne della matrice può variare in base alle convenzioni usate da ogni simulatore che supporta questa operazione.</span><span class="sxs-lookup"><span data-stu-id="55613-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>
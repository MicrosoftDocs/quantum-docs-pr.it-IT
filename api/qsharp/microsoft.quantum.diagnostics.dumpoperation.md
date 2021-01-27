---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operazione DumpOperation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829285"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="075fd-102">Operazione DumpOperation</span><span class="sxs-lookup"><span data-stu-id="075fd-102">DumpOperation operation</span></span>

<span data-ttu-id="075fd-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="075fd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="075fd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="075fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="075fd-105">Data un'operazione, Visualizza la diagnostica sull'operazione resa disponibile dalla destinazione di esecuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="075fd-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="075fd-106">Input</span><span class="sxs-lookup"><span data-stu-id="075fd-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="075fd-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="075fd-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="075fd-108">Numero di qubits su cui agisce l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="075fd-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="075fd-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="075fd-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="075fd-110">Operazione da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="075fd-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="075fd-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="075fd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="075fd-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="075fd-112">Example</span></span>

<span data-ttu-id="075fd-113">Quando viene eseguito sulla destinazione del simulatore Quantum, il frammento di codice seguente restituirà la matrice $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned}.</span><span class="sxs-lookup"><span data-stu-id="075fd-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="075fd-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="075fd-114">Remarks</span></span>

<span data-ttu-id="075fd-115">La chiamata a questa operazione non ha alcun effetto osservabile da Q #.</span><span class="sxs-lookup"><span data-stu-id="075fd-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="075fd-116">La diagnostica esatta visualizzata, se presente, dipende dalla destinazione di esecuzione corrente e dall'ambiente dell'editor.</span><span class="sxs-lookup"><span data-stu-id="075fd-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="075fd-117">Ad esempio, se usato nel simulatore Quantum a stato completo, viene visualizzata una matrice unitaria usata per rappresentare `op` .</span><span class="sxs-lookup"><span data-stu-id="075fd-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="075fd-118">Si noti che, quando vengono eseguiti su simulatori che ammettono un'ambiguità di una fase globale (ad esempio, il simulatore di stato completo), le rappresentazioni restituite possono variare fino a una fase globale.</span><span class="sxs-lookup"><span data-stu-id="075fd-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="075fd-119">Analogamente, l'ordine delle rappresentazioni di righe e colonne della matrice può variare in base alle convenzioni usate da ogni simulatore che supporta questa operazione.</span><span class="sxs-lookup"><span data-stu-id="075fd-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>
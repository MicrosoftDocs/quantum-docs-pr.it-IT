---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operazione ApplySeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841504"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="8dfa4-102">Operazione ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="8dfa4-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="8dfa4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8dfa4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8dfa4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8dfa4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8dfa4-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8dfa4-106">Input</span><span class="sxs-lookup"><span data-stu-id="8dfa4-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="8dfa4-107">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="8dfa4-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="8dfa4-108">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="8dfa4-109">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="8dfa4-110">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="8dfa4-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="8dfa4-111">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="8dfa4-112">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="8dfa4-113">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="8dfa4-113">register : 'T[]</span></span>

<span data-ttu-id="8dfa4-114">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="8dfa4-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8dfa4-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8dfa4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8dfa4-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8dfa4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8dfa4-117">T</span><span class="sxs-lookup"><span data-stu-id="8dfa4-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="8dfa4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="8dfa4-118">Example</span></span>

<span data-ttu-id="8dfa4-119">Il codice seguente applica exp ([PauliX, Pauliy], 0,5) a qubits 0, 1//Then X a qubit 2 Let Ops = [Exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubit (X, _)]; Let indici = [[0, 1], [2]]; ApplySeriesOfOps (OPS, indici, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="8dfa4-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="8dfa4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dfa4-120">See Also</span></span>

- [<span data-ttu-id="8dfa4-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="8dfa4-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)
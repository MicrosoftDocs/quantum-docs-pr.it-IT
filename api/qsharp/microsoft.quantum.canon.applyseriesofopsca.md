---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operazione ApplySeriesOfOpsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850859"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="eca74-102">Operazione ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="eca74-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="eca74-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eca74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eca74-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eca74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eca74-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="eca74-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="eca74-106">(Contiguo + controllato)</span><span class="sxs-lookup"><span data-stu-id="eca74-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="eca74-107">Input</span><span class="sxs-lookup"><span data-stu-id="eca74-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="eca74-108">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="eca74-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="eca74-109">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="eca74-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="eca74-110">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="eca74-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="eca74-111">Ogni deve avere un Funct e un functor controllato.</span><span class="sxs-lookup"><span data-stu-id="eca74-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="eca74-112">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="eca74-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="eca74-113">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="eca74-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="eca74-114">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="eca74-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="eca74-115">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="eca74-115">register : 'T[]</span></span>

<span data-ttu-id="eca74-116">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="eca74-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eca74-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eca74-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eca74-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="eca74-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eca74-119">T</span><span class="sxs-lookup"><span data-stu-id="eca74-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="eca74-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="eca74-120">Example</span></span>

<span data-ttu-id="eca74-121">Il codice seguente applica exp ([PauliX, Pauliy], 0,5) a qubits 0, 1//Then X a qubit 2 Let Ops = [Exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubitCA (X, _)]; Let indici = [[0, 1], [2]]; ApplySeriesOfOpsCA (OPS, indici, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="eca74-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitCA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsCA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="eca74-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca74-122">See Also</span></span>

- [<span data-ttu-id="eca74-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="eca74-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)
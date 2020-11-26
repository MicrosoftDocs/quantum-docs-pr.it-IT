---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Operazione ApplyOpRepeatedlyOverA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 65675a3a83f0ac730b9e3a58f80f77c096c1ce57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209146"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="3c738-102">Operazione ApplyOpRepeatedlyOverA</span><span class="sxs-lookup"><span data-stu-id="3c738-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="3c738-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c738-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c738-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c738-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c738-105">Applica più volte la stessa operazione su un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="3c738-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3c738-106">Input</span><span class="sxs-lookup"><span data-stu-id="3c738-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="3c738-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="3c738-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3c738-108">Un'operazione da applicare più volte nel registro qubit</span><span class="sxs-lookup"><span data-stu-id="3c738-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="3c738-109">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="3c738-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="3c738-110">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="3c738-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="3c738-111">Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.</span><span class="sxs-lookup"><span data-stu-id="3c738-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3c738-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c738-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c738-113">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="3c738-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c738-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c738-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3c738-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c738-115">See Also</span></span>

- [<span data-ttu-id="3c738-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="3c738-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
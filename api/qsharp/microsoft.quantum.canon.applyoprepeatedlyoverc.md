---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operazione ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717828"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="fb13d-102">Operazione ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="fb13d-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="fb13d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fb13d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fb13d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb13d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb13d-105">Applica più volte la stessa operazione su un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="fb13d-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fb13d-106">Input</span><span class="sxs-lookup"><span data-stu-id="fb13d-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="fb13d-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb13d-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="fb13d-108">Un'operazione da applicare più volte nel registro qubit</span><span class="sxs-lookup"><span data-stu-id="fb13d-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="fb13d-109">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="fb13d-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="fb13d-110">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="fb13d-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="fb13d-111">Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.</span><span class="sxs-lookup"><span data-stu-id="fb13d-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fb13d-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fb13d-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fb13d-113">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="fb13d-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb13d-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb13d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fb13d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb13d-115">See Also</span></span>

- [<span data-ttu-id="fb13d-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="fb13d-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
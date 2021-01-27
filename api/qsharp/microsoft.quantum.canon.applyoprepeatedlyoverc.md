---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operazione ApplyOpRepeatedlyOverC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 1cf3f32f0d25c1b4437f2bdbd93171a1a2e1e760
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844784"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="8c2d8-102">Operazione ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="8c2d8-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="8c2d8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c2d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c2d8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c2d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c2d8-105">Applica più volte la stessa operazione su un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="8c2d8-106">Input</span><span class="sxs-lookup"><span data-stu-id="8c2d8-106">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="8c2d8-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="8c2d8-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8c2d8-108">Un'operazione da applicare più volte nel registro qubit</span><span class="sxs-lookup"><span data-stu-id="8c2d8-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="8c2d8-109">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="8c2d8-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="8c2d8-110">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="8c2d8-111">Ogni matrice deve contenere un elenco di int che descrivono il qubits da usare.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8c2d8-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8c2d8-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8c2d8-113">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c2d8-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c2d8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8c2d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c2d8-115">See Also</span></span>

- [<span data-ttu-id="8c2d8-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="8c2d8-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)
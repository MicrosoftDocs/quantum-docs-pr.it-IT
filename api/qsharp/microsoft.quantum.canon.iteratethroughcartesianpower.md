---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operazione IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716022"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="bb5c0-102">Operazione IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="bb5c0-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="bb5c0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb5c0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb5c0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb5c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb5c0-105">Applica un'operazione per ogni indice nella potenza cartesiana di un intervallo di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="bb5c0-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="bb5c0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb5c0-106">Description</span></span>

<span data-ttu-id="bb5c0-107">Applica in modo iterativo un'operazione per ogni elemento di una potenza cartesiana dell'intervallo `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="bb5c0-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="bb5c0-108">Input</span><span class="sxs-lookup"><span data-stu-id="bb5c0-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="bb5c0-109">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb5c0-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb5c0-110">Potenza cartesiana a cui `0..(bound - 1)` deve essere generato l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="bb5c0-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="bb5c0-111">associato: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb5c0-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb5c0-112">Specifica dell'intervallo su cui eseguire l'iterazione, dato come lunghezza dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="bb5c0-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="bb5c0-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="bb5c0-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bb5c0-114">Operazione da chiamare per ogni elemento della potenza cartesiana specificata.</span><span class="sxs-lookup"><span data-stu-id="bb5c0-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb5c0-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb5c0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bb5c0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb5c0-116">See Also</span></span>

- [<span data-ttu-id="bb5c0-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="bb5c0-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)
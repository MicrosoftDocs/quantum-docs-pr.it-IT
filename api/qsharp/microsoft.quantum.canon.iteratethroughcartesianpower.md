---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operazione IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840292"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="ce655-102">Operazione IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="ce655-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="ce655-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce655-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce655-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce655-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce655-105">Applica un'operazione per ogni indice nella potenza cartesiana di un intervallo di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="ce655-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="ce655-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce655-106">Description</span></span>

<span data-ttu-id="ce655-107">Applica in modo iterativo un'operazione per ogni elemento di una potenza cartesiana dell'intervallo `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="ce655-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="ce655-108">Input</span><span class="sxs-lookup"><span data-stu-id="ce655-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="ce655-109">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce655-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce655-110">Potenza cartesiana a cui `0..(bound - 1)` deve essere generato l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="ce655-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="ce655-111">associato: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce655-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce655-112">Specifica dell'intervallo su cui eseguire l'iterazione, dato come lunghezza dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="ce655-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="ce655-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ce655-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ce655-114">Operazione da chiamare per ogni elemento della potenza cartesiana specificata.</span><span class="sxs-lookup"><span data-stu-id="ce655-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce655-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce655-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ce655-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce655-116">Example</span></span>

<span data-ttu-id="ce655-117">Data un'operazione `op` , i due frammenti di codice seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="ce655-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="ce655-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce655-118">See Also</span></span>

- [<span data-ttu-id="ce655-119">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="ce655-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)
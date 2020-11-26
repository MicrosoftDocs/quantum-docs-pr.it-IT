---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205814"
---
# <a name="operationpow-function"></a><span data-ttu-id="e24a9-102">OperationPow (funzione)</span><span class="sxs-lookup"><span data-stu-id="e24a9-102">OperationPow function</span></span>

<span data-ttu-id="e24a9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e24a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e24a9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e24a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e24a9-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="e24a9-105">Raises an operation to a power.</span></span>

<span data-ttu-id="e24a9-106">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="e24a9-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="e24a9-107">Input</span><span class="sxs-lookup"><span data-stu-id="e24a9-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e24a9-108">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e24a9-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e24a9-109">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="e24a9-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="e24a9-110">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e24a9-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e24a9-111">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e24a9-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="e24a9-112">Output:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e24a9-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e24a9-113">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="e24a9-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e24a9-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e24a9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e24a9-115">T</span><span class="sxs-lookup"><span data-stu-id="e24a9-115">'T</span></span>

<span data-ttu-id="e24a9-116">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="e24a9-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="e24a9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e24a9-117">See Also</span></span>

- [<span data-ttu-id="e24a9-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="e24a9-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="e24a9-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="e24a9-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="e24a9-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="e24a9-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)
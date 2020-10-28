---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715770"
---
# <a name="operationpow-function"></a><span data-ttu-id="8cdd5-102">OperationPow (funzione)</span><span class="sxs-lookup"><span data-stu-id="8cdd5-102">OperationPow function</span></span>

<span data-ttu-id="8cdd5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8cdd5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8cdd5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8cdd5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8cdd5-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-105">Raises an operation to a power.</span></span>

<span data-ttu-id="8cdd5-106">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="8cdd5-107">Input</span><span class="sxs-lookup"><span data-stu-id="8cdd5-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="8cdd5-108">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8cdd5-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8cdd5-109">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="8cdd5-110">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8cdd5-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8cdd5-111">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="8cdd5-112">Output:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8cdd5-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8cdd5-113">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8cdd5-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8cdd5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8cdd5-115">T</span><span class="sxs-lookup"><span data-stu-id="8cdd5-115">'T</span></span>

<span data-ttu-id="8cdd5-116">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="8cdd5-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cdd5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cdd5-117">See Also</span></span>

- [<span data-ttu-id="8cdd5-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="8cdd5-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="8cdd5-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="8cdd5-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="8cdd5-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="8cdd5-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)
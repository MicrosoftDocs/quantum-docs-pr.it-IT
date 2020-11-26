---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 71f66dd0098ab58d327fc33dbe5af191df0d3dc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205729"
---
# <a name="operationpowc-function"></a><span data-ttu-id="06c8e-102">OperationPowC (funzione)</span><span class="sxs-lookup"><span data-stu-id="06c8e-102">OperationPowC function</span></span>

<span data-ttu-id="06c8e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06c8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06c8e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06c8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06c8e-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="06c8e-105">Raises an operation to a power.</span></span>
<span data-ttu-id="06c8e-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="06c8e-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="06c8e-107">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="06c8e-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="06c8e-108">Input</span><span class="sxs-lookup"><span data-stu-id="06c8e-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="06c8e-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="06c8e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="06c8e-110">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="06c8e-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="06c8e-111">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06c8e-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06c8e-112">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="06c8e-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="06c8e-113">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="06c8e-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="06c8e-114">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="06c8e-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06c8e-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="06c8e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06c8e-116">T</span><span class="sxs-lookup"><span data-stu-id="06c8e-116">'T</span></span>

<span data-ttu-id="06c8e-117">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="06c8e-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="06c8e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06c8e-118">See Also</span></span>

- [<span data-ttu-id="06c8e-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="06c8e-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)
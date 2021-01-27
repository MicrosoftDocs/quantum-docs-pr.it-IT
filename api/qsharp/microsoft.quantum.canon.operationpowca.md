---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852317"
---
# <a name="operationpowca-function"></a><span data-ttu-id="c76e4-102">OperationPowCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="c76e4-102">OperationPowCA function</span></span>

<span data-ttu-id="c76e4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c76e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c76e4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c76e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c76e4-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="c76e4-105">Raises an operation to a power.</span></span>
<span data-ttu-id="c76e4-106">Il modificatore `A` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="c76e4-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="c76e4-107">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="c76e4-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="c76e4-108">Input</span><span class="sxs-lookup"><span data-stu-id="c76e4-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="c76e4-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c76e4-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c76e4-110">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="c76e4-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c76e4-111">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c76e4-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c76e4-112">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="c76e4-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="c76e4-113">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c76e4-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c76e4-114">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="c76e4-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c76e4-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c76e4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c76e4-116">T</span><span class="sxs-lookup"><span data-stu-id="c76e4-116">'T</span></span>

<span data-ttu-id="c76e4-117">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="c76e4-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="c76e4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c76e4-118">See Also</span></span>

- [<span data-ttu-id="c76e4-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="c76e4-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)
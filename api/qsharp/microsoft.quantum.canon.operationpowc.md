---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715686"
---
# <a name="operationpowc-function"></a><span data-ttu-id="0823c-102">OperationPowC (funzione)</span><span class="sxs-lookup"><span data-stu-id="0823c-102">OperationPowC function</span></span>

<span data-ttu-id="0823c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0823c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0823c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0823c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0823c-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="0823c-105">Raises an operation to a power.</span></span>
<span data-ttu-id="0823c-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="0823c-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="0823c-107">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="0823c-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0823c-108">Input</span><span class="sxs-lookup"><span data-stu-id="0823c-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="0823c-109">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0823c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0823c-110">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="0823c-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0823c-111">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0823c-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0823c-112">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="0823c-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="0823c-113">Output:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0823c-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0823c-114">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="0823c-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0823c-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0823c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0823c-116">T</span><span class="sxs-lookup"><span data-stu-id="0823c-116">'T</span></span>

<span data-ttu-id="0823c-117">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="0823c-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="0823c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0823c-118">See Also</span></span>

- [<span data-ttu-id="0823c-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="0823c-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)
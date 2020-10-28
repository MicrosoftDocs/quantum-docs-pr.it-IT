---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715714"
---
# <a name="operationpowa-function"></a><span data-ttu-id="71e3b-102">OperationPowA (funzione)</span><span class="sxs-lookup"><span data-stu-id="71e3b-102">OperationPowA function</span></span>

<span data-ttu-id="71e3b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71e3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71e3b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71e3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71e3b-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="71e3b-105">Raises an operation to a power.</span></span>
<span data-ttu-id="71e3b-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="71e3b-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="71e3b-107">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="71e3b-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="71e3b-108">Input</span><span class="sxs-lookup"><span data-stu-id="71e3b-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="71e3b-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="71e3b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71e3b-110">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="71e3b-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="71e3b-111">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71e3b-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71e3b-112">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="71e3b-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="71e3b-113">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="71e3b-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71e3b-114">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="71e3b-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="71e3b-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="71e3b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71e3b-116">T</span><span class="sxs-lookup"><span data-stu-id="71e3b-116">'T</span></span>

<span data-ttu-id="71e3b-117">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="71e3b-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="71e3b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71e3b-118">See Also</span></span>

- [<span data-ttu-id="71e3b-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="71e3b-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)
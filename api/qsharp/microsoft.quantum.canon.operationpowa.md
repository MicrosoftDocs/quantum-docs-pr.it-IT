---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205780"
---
# <a name="operationpowa-function"></a><span data-ttu-id="9e61c-102">OperationPowA (funzione)</span><span class="sxs-lookup"><span data-stu-id="9e61c-102">OperationPowA function</span></span>

<span data-ttu-id="9e61c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e61c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e61c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e61c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e61c-105">Genera un'operazione a potenza.</span><span class="sxs-lookup"><span data-stu-id="9e61c-105">Raises an operation to a power.</span></span>
<span data-ttu-id="9e61c-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="9e61c-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="9e61c-107">Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.</span><span class="sxs-lookup"><span data-stu-id="9e61c-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="9e61c-108">Input</span><span class="sxs-lookup"><span data-stu-id="9e61c-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="9e61c-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="9e61c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9e61c-110">Un'operazione $U $ che rappresenta il Gate da ripetere.</span><span class="sxs-lookup"><span data-stu-id="9e61c-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="9e61c-111">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e61c-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e61c-112">Il numero di volte in cui $U $ deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="9e61c-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="9e61c-113">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="9e61c-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9e61c-114">Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="9e61c-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9e61c-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9e61c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e61c-116">T</span><span class="sxs-lookup"><span data-stu-id="9e61c-116">'T</span></span>

<span data-ttu-id="9e61c-117">Tipo di operazione da alimentare.</span><span class="sxs-lookup"><span data-stu-id="9e61c-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e61c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e61c-118">See Also</span></span>

- [<span data-ttu-id="9e61c-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="9e61c-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)
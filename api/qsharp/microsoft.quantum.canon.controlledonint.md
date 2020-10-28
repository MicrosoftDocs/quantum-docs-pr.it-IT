---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716414"
---
# <a name="controlledonint-function"></a><span data-ttu-id="e5b41-102">ControlledOnInt (funzione)</span><span class="sxs-lookup"><span data-stu-id="e5b41-102">ControlledOnInt function</span></span>

<span data-ttu-id="e5b41-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e5b41-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e5b41-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5b41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5b41-105">Restituisce un operatore unitario che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.</span><span class="sxs-lookup"><span data-stu-id="e5b41-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e5b41-106">Input</span><span class="sxs-lookup"><span data-stu-id="e5b41-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="e5b41-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5b41-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5b41-108">Numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="e5b41-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="e5b41-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e5b41-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e5b41-110">Operatore unitario.</span><span class="sxs-lookup"><span data-stu-id="e5b41-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="e5b41-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e5b41-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e5b41-112">Operatore unitario che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde allo stato numerico `numberState` .</span><span class="sxs-lookup"><span data-stu-id="e5b41-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5b41-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e5b41-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5b41-114">T</span><span class="sxs-lookup"><span data-stu-id="e5b41-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e5b41-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="e5b41-115">Remarks</span></span>

<span data-ttu-id="e5b41-116">Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="e5b41-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>
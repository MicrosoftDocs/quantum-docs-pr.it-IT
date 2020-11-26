---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207259"
---
# <a name="controlledonint-function"></a><span data-ttu-id="57aeb-102">ControlledOnInt (funzione)</span><span class="sxs-lookup"><span data-stu-id="57aeb-102">ControlledOnInt function</span></span>

<span data-ttu-id="57aeb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57aeb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57aeb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57aeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57aeb-105">Restituisce un operatore unitario che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.</span><span class="sxs-lookup"><span data-stu-id="57aeb-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="57aeb-106">Input</span><span class="sxs-lookup"><span data-stu-id="57aeb-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="57aeb-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57aeb-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57aeb-108">Numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="57aeb-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="57aeb-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="57aeb-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="57aeb-110">Operatore unitario.</span><span class="sxs-lookup"><span data-stu-id="57aeb-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="57aeb-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="57aeb-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="57aeb-112">Operatore unitario che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde allo stato numerico `numberState` .</span><span class="sxs-lookup"><span data-stu-id="57aeb-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="57aeb-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="57aeb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57aeb-114">T</span><span class="sxs-lookup"><span data-stu-id="57aeb-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="57aeb-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="57aeb-115">Remarks</span></span>

<span data-ttu-id="57aeb-116">Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="57aeb-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>
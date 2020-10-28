---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operazione ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718350"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="55fa4-102">Operazione ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="55fa4-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="55fa4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55fa4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55fa4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55fa4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55fa4-105">Applica un'operazione unitaria nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.</span><span class="sxs-lookup"><span data-stu-id="55fa4-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="55fa4-106">Input</span><span class="sxs-lookup"><span data-stu-id="55fa4-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="55fa4-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55fa4-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55fa4-108">Intero non negativo in cui `oracle` deve essere controllata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="55fa4-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="55fa4-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="55fa4-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="55fa4-110">Operazione unitaria da controllare.</span><span class="sxs-lookup"><span data-stu-id="55fa4-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="55fa4-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="55fa4-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="55fa4-112">Registro Quantum che controlla l'applicazione di `oracle` .</span><span class="sxs-lookup"><span data-stu-id="55fa4-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="55fa4-113">targetRegister: t</span><span class="sxs-lookup"><span data-stu-id="55fa4-113">targetRegister : 'T</span></span>

<span data-ttu-id="55fa4-114">Registro su cui applicare `oracle` .</span><span class="sxs-lookup"><span data-stu-id="55fa4-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55fa4-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55fa4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55fa4-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="55fa4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55fa4-117">T</span><span class="sxs-lookup"><span data-stu-id="55fa4-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="55fa4-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="55fa4-118">Remarks</span></span>

<span data-ttu-id="55fa4-119">Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="55fa4-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="55fa4-120">`numberState` deve essere al massimo $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="55fa4-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="55fa4-121">Ad esempio, `numberState = 537` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="55fa4-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>
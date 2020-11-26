---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operazione ApplyControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219006"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="719d9-102">Operazione ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="719d9-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="719d9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="719d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="719d9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="719d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="719d9-105">Applica un'operazione unitaria nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.</span><span class="sxs-lookup"><span data-stu-id="719d9-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="719d9-106">Input</span><span class="sxs-lookup"><span data-stu-id="719d9-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="719d9-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="719d9-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="719d9-108">Intero non negativo in cui `oracle` deve essere controllata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="719d9-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="719d9-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="719d9-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="719d9-110">Operazione unitaria da controllare.</span><span class="sxs-lookup"><span data-stu-id="719d9-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="719d9-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="719d9-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="719d9-112">Registro Quantum che controlla l'applicazione di `oracle` .</span><span class="sxs-lookup"><span data-stu-id="719d9-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="719d9-113">targetRegister: t</span><span class="sxs-lookup"><span data-stu-id="719d9-113">targetRegister : 'T</span></span>

<span data-ttu-id="719d9-114">Registro su cui applicare `oracle` .</span><span class="sxs-lookup"><span data-stu-id="719d9-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="719d9-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="719d9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="719d9-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="719d9-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="719d9-117">T</span><span class="sxs-lookup"><span data-stu-id="719d9-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="719d9-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="719d9-118">Remarks</span></span>

<span data-ttu-id="719d9-119">Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="719d9-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="719d9-120">`numberState` deve essere al massimo $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="719d9-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="719d9-121">Ad esempio, `numberState = 537` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="719d9-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>
---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operazione ApplyControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718359"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="6211d-102">Operazione ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="6211d-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="6211d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6211d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6211d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6211d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6211d-105">Applica un'operazione unitaria nel registro di destinazione, controllata su uno stato specificato da una maschera di bit specificata.</span><span class="sxs-lookup"><span data-stu-id="6211d-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="6211d-106">Input</span><span class="sxs-lookup"><span data-stu-id="6211d-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="6211d-107">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6211d-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6211d-108">Stringa di bit per controllare l'operazione unitaria specificata su.</span><span class="sxs-lookup"><span data-stu-id="6211d-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="6211d-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6211d-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6211d-110">Operazione unitaria da applicare al registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6211d-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="6211d-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6211d-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6211d-112">Registro Quantum che controlla l'applicazione di `oracle` .</span><span class="sxs-lookup"><span data-stu-id="6211d-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="6211d-113">targetRegister: t</span><span class="sxs-lookup"><span data-stu-id="6211d-113">targetRegister : 'T</span></span>

<span data-ttu-id="6211d-114">Registro di destinazione da passare a `oracle` come input.</span><span class="sxs-lookup"><span data-stu-id="6211d-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6211d-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6211d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6211d-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6211d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6211d-117">T</span><span class="sxs-lookup"><span data-stu-id="6211d-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6211d-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="6211d-118">Remarks</span></span>

<span data-ttu-id="6211d-119">Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="6211d-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="6211d-120">Se `bits` è più lungo di `controlRegister` , viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="6211d-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="6211d-121">Ad esempio, `bits = [0,1,0,0,1]` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="6211d-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>
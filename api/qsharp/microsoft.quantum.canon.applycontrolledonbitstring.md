---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operazione ApplyControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841935"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="749f8-102">Operazione ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="749f8-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="749f8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="749f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="749f8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="749f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="749f8-105">Applica un'operazione unitaria nel registro di destinazione, controllata su uno stato specificato da una maschera di bit specificata.</span><span class="sxs-lookup"><span data-stu-id="749f8-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="749f8-106">Input</span><span class="sxs-lookup"><span data-stu-id="749f8-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="749f8-107">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="749f8-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="749f8-108">Stringa di bit per controllare l'operazione unitaria specificata su.</span><span class="sxs-lookup"><span data-stu-id="749f8-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="749f8-109">Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="749f8-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="749f8-110">Operazione unitaria da applicare al registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="749f8-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="749f8-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="749f8-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="749f8-112">Registro Quantum che controlla l'applicazione di `oracle` .</span><span class="sxs-lookup"><span data-stu-id="749f8-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="749f8-113">targetRegister: t</span><span class="sxs-lookup"><span data-stu-id="749f8-113">targetRegister : 'T</span></span>

<span data-ttu-id="749f8-114">Registro di destinazione da passare a `oracle` come input.</span><span class="sxs-lookup"><span data-stu-id="749f8-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="749f8-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="749f8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="749f8-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="749f8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="749f8-117">T</span><span class="sxs-lookup"><span data-stu-id="749f8-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="749f8-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="749f8-118">Remarks</span></span>

<span data-ttu-id="749f8-119">Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="749f8-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="749f8-120">Se `bits` è più lungo di `controlRegister` , viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="749f8-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="749f8-121">Ad esempio, `bits = [0,1,0,0,1]` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="749f8-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>
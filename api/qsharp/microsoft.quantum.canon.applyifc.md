---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operazione ApplyIfC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841850"
---
# <a name="applyifc-operation"></a><span data-ttu-id="f924d-102">Operazione ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f924d-102">ApplyIfC operation</span></span>

<span data-ttu-id="f924d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f924d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f924d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f924d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f924d-105">Applica un'operazione controllabile condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="f924d-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f924d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f924d-106">Description</span></span>

<span data-ttu-id="f924d-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="f924d-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="f924d-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="f924d-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f924d-109">Il suffisso `C` indica che l'operazione da applicare è controllabile.</span><span class="sxs-lookup"><span data-stu-id="f924d-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f924d-110">Input</span><span class="sxs-lookup"><span data-stu-id="f924d-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f924d-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="f924d-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f924d-112">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="f924d-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="f924d-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f924d-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f924d-114">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="f924d-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="f924d-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="f924d-115">target : 'T</span></span>

<span data-ttu-id="f924d-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f924d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f924d-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f924d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f924d-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f924d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f924d-119">T</span><span class="sxs-lookup"><span data-stu-id="f924d-119">'T</span></span>

<span data-ttu-id="f924d-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="f924d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="f924d-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f924d-121">Example</span></span>

<span data-ttu-id="f924d-122">Il codice seguente prepara un registro di qubits in uno stato di base computazionale rappresentato da una stringa di bit classica specificata come matrice di `Bool` valori:</span><span class="sxs-lookup"><span data-stu-id="f924d-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="f924d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f924d-123">See Also</span></span>

- [<span data-ttu-id="f924d-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f924d-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="f924d-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="f924d-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="f924d-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="f924d-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)
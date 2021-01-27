---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operazione ApplyIfCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844994"
---
# <a name="applyifca-operation"></a><span data-ttu-id="64bcb-102">Operazione ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="64bcb-102">ApplyIfCA operation</span></span>

<span data-ttu-id="64bcb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64bcb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64bcb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64bcb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64bcb-105">Applica un'operazione unitaria condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="64bcb-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="64bcb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64bcb-106">Description</span></span>

<span data-ttu-id="64bcb-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="64bcb-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="64bcb-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="64bcb-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="64bcb-109">Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).</span><span class="sxs-lookup"><span data-stu-id="64bcb-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="64bcb-110">Input</span><span class="sxs-lookup"><span data-stu-id="64bcb-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="64bcb-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="64bcb-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="64bcb-112">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="64bcb-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="64bcb-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64bcb-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64bcb-114">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="64bcb-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="64bcb-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="64bcb-115">target : 'T</span></span>

<span data-ttu-id="64bcb-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="64bcb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64bcb-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64bcb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="64bcb-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="64bcb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64bcb-119">T</span><span class="sxs-lookup"><span data-stu-id="64bcb-119">'T</span></span>

<span data-ttu-id="64bcb-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="64bcb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="64bcb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="64bcb-121">Example</span></span>

<span data-ttu-id="64bcb-122">Il codice seguente prepara un registro di qubits in uno stato di base computazionale rappresentato da una stringa di bit classica specificata come matrice di `Bool` valori:</span><span class="sxs-lookup"><span data-stu-id="64bcb-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="64bcb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64bcb-123">See Also</span></span>

- [<span data-ttu-id="64bcb-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="64bcb-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="64bcb-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="64bcb-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="64bcb-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="64bcb-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)
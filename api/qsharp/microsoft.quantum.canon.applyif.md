---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operazione ApplyIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841877"
---
# <a name="applyif-operation"></a><span data-ttu-id="25192-102">Operazione ApplyIf</span><span class="sxs-lookup"><span data-stu-id="25192-102">ApplyIf operation</span></span>

<span data-ttu-id="25192-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25192-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25192-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25192-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25192-105">Applica un'operazione condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="25192-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="25192-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25192-106">Description</span></span>

<span data-ttu-id="25192-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="25192-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="25192-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="25192-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="25192-109">Input</span><span class="sxs-lookup"><span data-stu-id="25192-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="25192-110">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="25192-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="25192-111">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="25192-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="25192-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="25192-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="25192-113">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="25192-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="25192-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="25192-114">target : 'T</span></span>

<span data-ttu-id="25192-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="25192-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25192-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25192-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25192-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="25192-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25192-118">T</span><span class="sxs-lookup"><span data-stu-id="25192-118">'T</span></span>

<span data-ttu-id="25192-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="25192-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="25192-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="25192-120">Example</span></span>

<span data-ttu-id="25192-121">Il codice seguente prepara un registro di qubits in uno stato di base computazionale rappresentato da una stringa di bit classica specificata come matrice di `Bool` valori:</span><span class="sxs-lookup"><span data-stu-id="25192-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="25192-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25192-122">See Also</span></span>

- [<span data-ttu-id="25192-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="25192-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="25192-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="25192-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="25192-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="25192-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)
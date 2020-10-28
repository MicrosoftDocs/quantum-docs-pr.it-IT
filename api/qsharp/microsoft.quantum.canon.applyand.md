---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operazione selezionerò
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718458"
---
# <a name="applyand-operation"></a><span data-ttu-id="c9abd-102">Operazione selezionerò</span><span class="sxs-lookup"><span data-stu-id="c9abd-102">ApplyAnd operation</span></span>

<span data-ttu-id="c9abd-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9abd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9abd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9abd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9abd-105">Inverte un qubit di destinazione specificato se e solo se entrambi i qubits di controllo si trovano nello stato 1, usando la misurazione per eseguire l'operazione contigua.</span><span class="sxs-lookup"><span data-stu-id="c9abd-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c9abd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9abd-106">Description</span></span>

<span data-ttu-id="c9abd-107">Inverte `target` se e solo se entrambi i controlli sono pari a 1, ma presuppone che `target` si trovi nello stato 0.</span><span class="sxs-lookup"><span data-stu-id="c9abd-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="c9abd-108">L'operazione ha T-Count 4, T-Depth 2 e non richiede qubit helper e può pertanto essere preferibile a un'operazione CCNOT, se `target` è noto come 0.</span><span class="sxs-lookup"><span data-stu-id="c9abd-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="c9abd-109">Il contiguo di questa operazione è basato sulla misurazione e non richiede alcun controllo T.</span><span class="sxs-lookup"><span data-stu-id="c9abd-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="c9abd-110">Per l'applicazione controllata di questa operazione non è richiesto alcun supporto qubit, `2^c` `Rz` Gates e non è ottimizzato per la profondità, dove `c` è il numero di qubits del controllo complessivo, inclusi i due controlli dell' `ApplyAnd` operazione.</span><span class="sxs-lookup"><span data-stu-id="c9abd-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="c9abd-111">L'applicazione controllata contigua richiede i controlli `2^c - 1` `Rz` (con un angolo doppio della dimensione dell'operazione non contigua), nessun helper qubit e non è ottimizzato per la profondità.</span><span class="sxs-lookup"><span data-stu-id="c9abd-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="c9abd-112">Input</span><span class="sxs-lookup"><span data-stu-id="c9abd-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="c9abd-113">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9abd-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9abd-114">Primo controllo qubit</span><span class="sxs-lookup"><span data-stu-id="c9abd-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="c9abd-115">controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9abd-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9abd-116">Secondo qubit di controllo</span><span class="sxs-lookup"><span data-stu-id="c9abd-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c9abd-117">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9abd-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9abd-118">Qubit ausiliari di destinazione; deve essere nello stato 0</span><span class="sxs-lookup"><span data-stu-id="c9abd-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9abd-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9abd-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c9abd-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c9abd-120">References</span></span>

- <span data-ttu-id="c9abd-121">Cody Jones: "costruzioni innovative per il controllo Toffoli A tolleranza di errore", fisico. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="c9abd-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="c9abd-122">Craig Gidney: "dimezzando il costo di aggiunta Quantum", Quantum 2, pagina 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="c9abd-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="c9abd-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree pattern", [articolo del Blog del 19 dicembre 2019](https://msoeken.github.io/blog_qac.html) (Nota: spiega la costruzione a più controlli)</span><span class="sxs-lookup"><span data-stu-id="c9abd-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>
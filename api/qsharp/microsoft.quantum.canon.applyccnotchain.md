---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Operazione ApplyCCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845131"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="ef469-102">Operazione ApplyCCNOTChain</span><span class="sxs-lookup"><span data-stu-id="ef469-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="ef469-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef469-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef469-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef469-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef469-105">Implementa una cascata di controlli CCNOT controllati sui bit corrispondenti di due registri qubit, agendo sul qubit successivo di uno dei registri.</span><span class="sxs-lookup"><span data-stu-id="ef469-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="ef469-106">A partire da qubits nella posizione 0 in entrambi i registri come controlli, CCNOT viene applicato a qubit nella posizione 1 del registro di destinazione, quindi controllato da qubits nella posizione 1 che agisce su qubit nella posizione 2 nel registro di destinazione e così via, terminando con un'azione sul qubit di destinazione in posizione `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="ef469-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ef469-107">Input</span><span class="sxs-lookup"><span data-stu-id="ef469-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ef469-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef469-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef469-109">Qubit Register, usato solo per i controlli.</span><span class="sxs-lookup"><span data-stu-id="ef469-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="ef469-110">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef469-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef469-111">Registro qubit, usato per i controlli e come destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef469-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef469-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef469-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ef469-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="ef469-113">Remarks</span></span>

<span data-ttu-id="ef469-114">Il registro qubit di destinazione deve avere un qubit maggiore di quello dell'altro.</span><span class="sxs-lookup"><span data-stu-id="ef469-114">The target qubit register must have one qubit more than the other register.</span></span>
---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operazione CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711539"
---
# <a name="ccnot-operation"></a><span data-ttu-id="ff45b-102">Operazione CCNOT</span><span class="sxs-lookup"><span data-stu-id="ff45b-102">CCNOT operation</span></span>

<span data-ttu-id="ff45b-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ff45b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ff45b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff45b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff45b-105">Applica il Gate CCNOT (doppiamente controllata) a tre qubits.</span><span class="sxs-lookup"><span data-stu-id="ff45b-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ff45b-106">Input</span><span class="sxs-lookup"><span data-stu-id="ff45b-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="ff45b-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff45b-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff45b-108">Primo controllo qubit per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="ff45b-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="ff45b-109">controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff45b-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff45b-110">Secondo qubit di controllo per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="ff45b-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ff45b-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff45b-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff45b-112">Qubit di destinazione per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="ff45b-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff45b-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff45b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff45b-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="ff45b-114">Remarks</span></span>

<span data-ttu-id="ff45b-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="ff45b-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```
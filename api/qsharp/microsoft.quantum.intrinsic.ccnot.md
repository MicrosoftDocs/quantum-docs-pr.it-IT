---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operazione CCNOT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212478"
---
# <a name="ccnot-operation"></a><span data-ttu-id="76338-102">Operazione CCNOT</span><span class="sxs-lookup"><span data-stu-id="76338-102">CCNOT operation</span></span>

<span data-ttu-id="76338-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="76338-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="76338-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="76338-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="76338-105">Applica il Gate CCNOT (doppiamente controllata) a tre qubits.</span><span class="sxs-lookup"><span data-stu-id="76338-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76338-106">Input</span><span class="sxs-lookup"><span data-stu-id="76338-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="76338-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76338-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76338-108">Primo controllo qubit per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="76338-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="76338-109">controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76338-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76338-110">Secondo qubit di controllo per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="76338-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="76338-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76338-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76338-112">Qubit di destinazione per CCNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="76338-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76338-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76338-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76338-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="76338-114">Remarks</span></span>

<span data-ttu-id="76338-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="76338-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```
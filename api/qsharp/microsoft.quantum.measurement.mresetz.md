---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operazione MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194135"
---
# <a name="mresetz-operation"></a><span data-ttu-id="e870d-102">Operazione MResetZ</span><span class="sxs-lookup"><span data-stu-id="e870d-102">MResetZ operation</span></span>

<span data-ttu-id="e870d-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e870d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e870d-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e870d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e870d-105">Misura un singolo qubit in base alla Z e lo reimposta su uno stato iniziale fisso dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="e870d-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="e870d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e870d-106">Description</span></span>

<span data-ttu-id="e870d-107">Esegue una misurazione a qubit singolo in $Z $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="e870d-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="e870d-108">Input</span><span class="sxs-lookup"><span data-stu-id="e870d-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="e870d-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e870d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e870d-110">Singolo qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="e870d-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e870d-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="e870d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e870d-112">Risultato della misurazione `target` in Pauli $Z $ base.</span><span class="sxs-lookup"><span data-stu-id="e870d-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>
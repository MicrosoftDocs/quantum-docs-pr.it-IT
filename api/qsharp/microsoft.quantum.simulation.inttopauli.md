---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229206"
---
# <a name="inttopauli-function"></a><span data-ttu-id="9fb92-102">IntToPauli (funzione)</span><span class="sxs-lookup"><span data-stu-id="9fb92-102">IntToPauli function</span></span>

<span data-ttu-id="9fb92-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9fb92-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9fb92-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fb92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fb92-105">Converte un Integer in un operatore Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="9fb92-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="9fb92-106">Input</span><span class="sxs-lookup"><span data-stu-id="9fb92-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="9fb92-107">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9fb92-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9fb92-108">Integer nell'intervallo `0..3` da convertire in operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="9fb92-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="9fb92-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9fb92-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9fb92-110">`Pauli`Operatore fornito da `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="9fb92-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>
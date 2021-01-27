---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842233"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="c6bf3-102">IntsToPaulis (funzione)</span><span class="sxs-lookup"><span data-stu-id="c6bf3-102">IntsToPaulis function</span></span>

<span data-ttu-id="c6bf3-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c6bf3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c6bf3-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6bf3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6bf3-105">Converte una matrice di numeri interi in una matrice di operatori Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="c6bf3-106">Input</span><span class="sxs-lookup"><span data-stu-id="c6bf3-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="c6bf3-107">int: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c6bf3-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c6bf3-108">Matrice di numeri interi nell'intervallo `0..3`  da convertire in operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c6bf3-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c6bf3-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c6bf3-110">Matrice `paulis` di operatori Pauli `Pauli[]` la cui lunghezza `ints` `paulis[idxPauli]` è uguale all'elemento di `[PauliI, PauliX, PauliY, PauliZ]` specificato da `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="c6bf3-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>
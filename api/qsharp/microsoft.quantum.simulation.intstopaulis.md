---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709453"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="47a40-102">IntsToPaulis (funzione)</span><span class="sxs-lookup"><span data-stu-id="47a40-102">IntsToPaulis function</span></span>

<span data-ttu-id="47a40-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="47a40-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="47a40-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47a40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47a40-105">Converte una matrice di numeri interi in una matrice di operatori Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="47a40-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="47a40-106">Input</span><span class="sxs-lookup"><span data-stu-id="47a40-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="47a40-107">int: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="47a40-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="47a40-108">Matrice di numeri interi nell'intervallo `0..3`  da convertire in operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="47a40-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="47a40-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="47a40-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="47a40-110">Matrice `paulis` di operatori Pauli `Pauli[]` la cui lunghezza `ints` `paulis[idxPauli]` è uguale all'elemento di `[PauliI, PauliX, PauliY, PauliZ]` specificato da `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="47a40-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>
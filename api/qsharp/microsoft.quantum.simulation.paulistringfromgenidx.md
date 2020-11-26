---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230311"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="62ce2-102">PauliStringFromGenIdx (funzione)</span><span class="sxs-lookup"><span data-stu-id="62ce2-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="62ce2-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="62ce2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="62ce2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62ce2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62ce2-105">Estrae la stringa Pauli e i relativi indici qubit di un termine di Pauli descritto da un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="62ce2-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="62ce2-106">Input</span><span class="sxs-lookup"><span data-stu-id="62ce2-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="62ce2-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="62ce2-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="62ce2-108">`GeneratorIndex` tipo che codifica un termine di Pauli.</span><span class="sxs-lookup"><span data-stu-id="62ce2-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="62ce2-109">Output: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="62ce2-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="62ce2-110">Stringa di Pauli del termine descritta da un oggetto `GeneratorIndex` e indici per il qubits su cui agisce.</span><span class="sxs-lookup"><span data-stu-id="62ce2-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>
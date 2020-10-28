---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710545"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="66c04-102">PauliStringFromGenIdx (funzione)</span><span class="sxs-lookup"><span data-stu-id="66c04-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="66c04-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="66c04-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="66c04-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66c04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66c04-105">Estrae la stringa Pauli e i relativi indici qubit di un termine di Pauli descritto da un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="66c04-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="66c04-106">Input</span><span class="sxs-lookup"><span data-stu-id="66c04-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="66c04-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="66c04-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="66c04-108">`GeneratorIndex` tipo che codifica un termine di Pauli.</span><span class="sxs-lookup"><span data-stu-id="66c04-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="66c04-109">Output: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="66c04-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="66c04-110">Stringa di Pauli del termine descritta da un oggetto `GeneratorIndex` e indici per il qubits su cui agisce.</span><span class="sxs-lookup"><span data-stu-id="66c04-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>
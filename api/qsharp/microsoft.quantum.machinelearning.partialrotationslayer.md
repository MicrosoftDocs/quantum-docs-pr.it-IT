---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722435"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="03aae-102">PartialRotationsLayer (funzione)</span><span class="sxs-lookup"><span data-stu-id="03aae-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="03aae-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="03aae-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="03aae-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03aae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03aae-105">Restituisce una matrice di rotazioni a qubit singolo lungo un asse specificato, parametrizzato da parametri di modello distinti.</span><span class="sxs-lookup"><span data-stu-id="03aae-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="03aae-106">Input</span><span class="sxs-lookup"><span data-stu-id="03aae-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="03aae-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="03aae-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="03aae-108">Indici per il qubits da usare come destinazioni per ogni rotazione.</span><span class="sxs-lookup"><span data-stu-id="03aae-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="03aae-109">asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="03aae-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="03aae-110">Asse di rotazione per ogni rotazione nel livello specificato.</span><span class="sxs-lookup"><span data-stu-id="03aae-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="03aae-111">Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="03aae-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="03aae-112">Matrice di rotazioni controllate sull'asse specificato, una per ogni `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="03aae-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>
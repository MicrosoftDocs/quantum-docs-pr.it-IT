---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211934"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="ee6fa-102">CyclicEntanglingLayer (funzione)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="ee6fa-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ee6fa-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ee6fa-105">Restituisce una matrice di rotazioni controllate singolarmente lungo un asse specificato, disposte ciclicamente in un registro di qubits e parametrizzato da parametri di modello distinti.</span><span class="sxs-lookup"><span data-stu-id="ee6fa-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="ee6fa-106">Input</span><span class="sxs-lookup"><span data-stu-id="ee6fa-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ee6fa-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee6fa-108">Numero di qubits di cui ha agito il livello specificato.</span><span class="sxs-lookup"><span data-stu-id="ee6fa-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="ee6fa-109">asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ee6fa-110">Asse di rotazione per ogni rotazione nel livello specificato.</span><span class="sxs-lookup"><span data-stu-id="ee6fa-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="ee6fa-111">stride: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee6fa-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee6fa-112">Separazione tra gli indici di destinazione e di controllo per ogni rotazione.</span><span class="sxs-lookup"><span data-stu-id="ee6fa-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="ee6fa-113">Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="ee6fa-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="ee6fa-114">Una matrice di rotazioni controllate da due qubit, disposti ciclicamente in un registro di `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="ee6fa-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>
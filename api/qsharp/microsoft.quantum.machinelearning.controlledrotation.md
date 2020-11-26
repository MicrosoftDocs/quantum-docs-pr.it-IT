---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definito dall'utente ControlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196566"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="a7f5a-102">Tipo definito dall'utente ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="a7f5a-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="a7f5a-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a7f5a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a7f5a-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a7f5a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a7f5a-105">Descrive una rotazione controllata in termini di indici di destinazione e di controllo, asse di rotazione e indice in un vettore di parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="a7f5a-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="a7f5a-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="a7f5a-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="a7f5a-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7f5a-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7f5a-108">Indice della qubit di destinazione per la rotazione controllata.</span><span class="sxs-lookup"><span data-stu-id="a7f5a-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="a7f5a-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a7f5a-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a7f5a-110">Matrice di indici qubit del controllo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="a7f5a-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="a7f5a-111">Asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a7f5a-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a7f5a-112">Asse della rotazione.</span><span class="sxs-lookup"><span data-stu-id="a7f5a-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="a7f5a-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7f5a-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7f5a-114">Indice in un vettore di parametri del modello che descrive l'angolo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="a7f5a-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7f5a-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a7f5a-115">Remarks</span></span>

<span data-ttu-id="a7f5a-116">Una rotazione non controllata può essere rappresentata impostando `ControlIndices` su una matrice vuota di indici, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="a7f5a-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>
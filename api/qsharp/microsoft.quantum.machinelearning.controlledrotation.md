---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definito dall'utente ControlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847406"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="d2bcb-102">Tipo definito dall'utente ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="d2bcb-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="d2bcb-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d2bcb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d2bcb-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d2bcb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d2bcb-105">Descrive una rotazione controllata in termini di indici di destinazione e di controllo, asse di rotazione e indice in un vettore di parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="d2bcb-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="d2bcb-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="d2bcb-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="d2bcb-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2bcb-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2bcb-108">Indice della qubit di destinazione per la rotazione controllata.</span><span class="sxs-lookup"><span data-stu-id="d2bcb-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="d2bcb-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d2bcb-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d2bcb-110">Matrice di indici qubit del controllo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcb-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="d2bcb-111">Asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d2bcb-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d2bcb-112">Asse della rotazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcb-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="d2bcb-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2bcb-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2bcb-114">Indice in un vettore di parametri del modello che descrive l'angolo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcb-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="d2bcb-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2bcb-115">Example</span></span>

<span data-ttu-id="d2bcb-116">Nell'esempio seguente viene rappresentata una rotazione relativa all'asse di $X $ del primo qubit in un registro, controllato sulla seconda qubit e con un angolo fornito dal quarto parametro in un modello sequenziale:</span><span class="sxs-lookup"><span data-stu-id="d2bcb-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="d2bcb-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="d2bcb-117">Remarks</span></span>

<span data-ttu-id="d2bcb-118">Una rotazione non controllata può essere rappresentata impostando `ControlIndices` su una matrice vuota di indici, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="d2bcb-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>
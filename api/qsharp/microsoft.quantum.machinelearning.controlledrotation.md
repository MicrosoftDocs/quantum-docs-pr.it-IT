---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definito dall'utente ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711360"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="3e618-102">Tipo definito dall'utente ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="3e618-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="3e618-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e618-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3e618-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e618-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e618-105">Descrive una rotazione controllata in termini di indici di destinazione e di controllo, asse di rotazione e indice in un vettore di parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="3e618-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="3e618-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="3e618-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="3e618-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e618-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e618-108">Indice della qubit di destinazione per la rotazione controllata.</span><span class="sxs-lookup"><span data-stu-id="3e618-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="3e618-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3e618-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3e618-110">Matrice di indici qubit del controllo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="3e618-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="3e618-111">Asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="3e618-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="3e618-112">Asse della rotazione.</span><span class="sxs-lookup"><span data-stu-id="3e618-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="3e618-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e618-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e618-114">Indice in un vettore di parametri del modello che descrive l'angolo per la rotazione.</span><span class="sxs-lookup"><span data-stu-id="3e618-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e618-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="3e618-115">Remarks</span></span>

<span data-ttu-id="3e618-116">Una rotazione non controllata può essere rappresentata impostando `ControlIndices` su una matrice vuota di indici, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="3e618-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>
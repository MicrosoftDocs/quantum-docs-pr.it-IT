---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definito dall'utente SequentialModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722393"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="1c47b-102">Tipo definito dall'utente SequentialModel</span><span class="sxs-lookup"><span data-stu-id="1c47b-102">SequentialModel user defined type</span></span>

<span data-ttu-id="1c47b-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1c47b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1c47b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c47b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c47b-105">Descrive un modello di classificazione quantistica costituito da una sequenza di rotazioni con parametri e controllate, da un'assegnazione di angoli di rotazione e da una distorsione tra le due classi riconosciute dal modello.</span><span class="sxs-lookup"><span data-stu-id="1c47b-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="1c47b-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="1c47b-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="1c47b-107">Struttura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1c47b-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1c47b-108">Sequenza di rotazioni controllate utilizzate per classificare gli input.</span><span class="sxs-lookup"><span data-stu-id="1c47b-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="1c47b-109">Parametri: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1c47b-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1c47b-110">Assegnazione degli angoli di rotazione alla struttura di classificazione specificata.</span><span class="sxs-lookup"><span data-stu-id="1c47b-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="1c47b-111">Distorsione: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1c47b-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1c47b-112">Distorsione tra le due classi riconosciute da questo classificatore.</span><span class="sxs-lookup"><span data-stu-id="1c47b-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="1c47b-113">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1c47b-113">References</span></span>

- [<span data-ttu-id="1c47b-114">arXiv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="1c47b-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)
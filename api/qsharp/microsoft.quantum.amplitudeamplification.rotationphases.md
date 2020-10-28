---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definito dall'utente RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721766"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="99fbe-102">Tipo definito dall'utente RotationPhases</span><span class="sxs-lookup"><span data-stu-id="99fbe-102">RotationPhases user defined type</span></span>

<span data-ttu-id="99fbe-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="99fbe-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="99fbe-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99fbe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99fbe-105">Fasi per una sequenza di rotazioni a singolo qubit nell'amplificazione dell'ampiezza.</span><span class="sxs-lookup"><span data-stu-id="99fbe-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="99fbe-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="99fbe-106">Remarks</span></span>

<span data-ttu-id="99fbe-107">Il primo parametro è una matrice di fasi per le riflessioni, espresso come prodotto di rotazioni a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="99fbe-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="99fbe-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="99fbe-108">[ G.H.</span></span> <span data-ttu-id="99fbe-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="99fbe-109">Low, I. L.</span></span> <span data-ttu-id="99fbe-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="99fbe-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>
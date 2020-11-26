---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definito dall'utente RotationPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191364"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="bcda2-102">Tipo definito dall'utente RotationPhases</span><span class="sxs-lookup"><span data-stu-id="bcda2-102">RotationPhases user defined type</span></span>

<span data-ttu-id="bcda2-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bcda2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bcda2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcda2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcda2-105">Fasi per una sequenza di rotazioni a singolo qubit nell'amplificazione dell'ampiezza.</span><span class="sxs-lookup"><span data-stu-id="bcda2-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="bcda2-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bcda2-106">Remarks</span></span>

<span data-ttu-id="bcda2-107">Il primo parametro è una matrice di fasi per le riflessioni, espresso come prodotto di rotazioni a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="bcda2-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="bcda2-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="bcda2-108">[ G.H.</span></span> <span data-ttu-id="bcda2-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="bcda2-109">Low, I. L.</span></span> <span data-ttu-id="bcda2-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="bcda2-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>
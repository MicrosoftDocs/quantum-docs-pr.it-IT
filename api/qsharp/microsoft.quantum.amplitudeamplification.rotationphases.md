---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Tipo definito dall'utente RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843973"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="c3dff-102">Tipo definito dall'utente RotationPhases</span><span class="sxs-lookup"><span data-stu-id="c3dff-102">RotationPhases user defined type</span></span>

<span data-ttu-id="c3dff-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c3dff-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c3dff-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3dff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3dff-105">Fasi per una sequenza di rotazioni a singolo qubit nell'amplificazione dell'ampiezza.</span><span class="sxs-lookup"><span data-stu-id="c3dff-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="c3dff-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="c3dff-106">Remarks</span></span>

<span data-ttu-id="c3dff-107">Il primo parametro è una matrice di fasi per le riflessioni, espresso come prodotto di rotazioni a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="c3dff-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="c3dff-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="c3dff-108">[ G.H.</span></span> <span data-ttu-id="c3dff-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="c3dff-109">Low, I. L.</span></span> <span data-ttu-id="c3dff-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="c3dff-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>
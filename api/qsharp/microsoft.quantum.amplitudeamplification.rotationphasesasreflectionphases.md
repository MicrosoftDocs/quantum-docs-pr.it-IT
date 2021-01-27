---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843946"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="3926f-102">RotationPhasesAsReflectionPhases (funzione)</span><span class="sxs-lookup"><span data-stu-id="3926f-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="3926f-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3926f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3926f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3926f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3926f-105">Converte le fasi specificate come rotazioni a qubit singolo in fasi specificate come riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="3926f-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="3926f-106">Input</span><span class="sxs-lookup"><span data-stu-id="3926f-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="3926f-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="3926f-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="3926f-108">Matrice di rotazioni a singolo qubit da convertire in riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="3926f-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="3926f-109">Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3926f-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3926f-110">Operazione che implementa le fasi specificate come riflessioni parziali.</span><span class="sxs-lookup"><span data-stu-id="3926f-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="3926f-111">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3926f-111">References</span></span>

<span data-ttu-id="3926f-112">La convenzione viene usata in</span><span class="sxs-lookup"><span data-stu-id="3926f-112">We use the convention in</span></span>

- <span data-ttu-id="3926f-113">[ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) per la correlazione di fasi di rotazione a qubit singolo alle fasi dell'operatore di Reflection.</span><span class="sxs-lookup"><span data-stu-id="3926f-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>
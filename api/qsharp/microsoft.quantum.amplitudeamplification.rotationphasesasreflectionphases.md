---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191194"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="8fe68-102">RotationPhasesAsReflectionPhases (funzione)</span><span class="sxs-lookup"><span data-stu-id="8fe68-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="8fe68-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8fe68-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8fe68-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8fe68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8fe68-105">Converte le fasi specificate come rotazioni a qubit singolo in fasi specificate come riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="8fe68-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="8fe68-106">Input</span><span class="sxs-lookup"><span data-stu-id="8fe68-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="8fe68-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="8fe68-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="8fe68-108">Matrice di rotazioni a singolo qubit da convertire in riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="8fe68-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="8fe68-109">Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8fe68-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="8fe68-110">Operazione che implementa le fasi specificate come riflessioni parziali.</span><span class="sxs-lookup"><span data-stu-id="8fe68-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="8fe68-111">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8fe68-111">References</span></span>

<span data-ttu-id="8fe68-112">La convenzione viene usata in</span><span class="sxs-lookup"><span data-stu-id="8fe68-112">We use the convention in</span></span>

- <span data-ttu-id="8fe68-113">[ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) per la correlazione di fasi di rotazione a qubit singolo alle fasi dell'operatore di Reflection.</span><span class="sxs-lookup"><span data-stu-id="8fe68-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>
---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721752"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases (funzione)

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Converte le fasi specificate come rotazioni a qubit singolo in fasi specificate come riflessi parziali.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Input

### <a name="rotphases--rotationphases"></a>rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Matrice di rotazioni a singolo qubit da convertire in riflessi parziali.



## <a name="output--reflectionphases"></a>Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Operazione che implementa le fasi specificate come riflessioni parziali.

## <a name="references"></a>Riferimenti

La convenzione viene usata in

- [ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) per la correlazione di fasi di rotazione a qubit singolo alle fasi dell'operatore di Reflection.
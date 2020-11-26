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
# <a name="rotationphases-user-defined-type"></a>Tipo definito dall'utente RotationPhases

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fasi per una sequenza di rotazioni a singolo qubit nell'amplificazione dell'ampiezza.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Osservazioni

Il primo parametro è una matrice di fasi per le riflessioni, espresso come prodotto di rotazioni a qubit singola.
[G.H. Low, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].
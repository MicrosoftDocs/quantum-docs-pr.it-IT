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
# <a name="rotationphases-user-defined-type"></a>Tipo definito dall'utente RotationPhases

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Fasi per una sequenza di rotazioni a singolo qubit nell'amplificazione dell'ampiezza.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Commenti

Il primo parametro è una matrice di fasi per le riflessioni, espresso come prodotto di rotazioni a qubit singola.
[G.H. Low, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].
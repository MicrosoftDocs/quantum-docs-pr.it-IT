---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Sampled (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722424"
---
# <a name="sampled-function"></a>Sampled (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Esegue il campionamento di una matrice specificata, usando la pianificazione specificata.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="schedule--samplingschedule"></a>pianificazione: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Pianificazione da utilizzare nei valori di campionamento.


### <a name="values--t"></a>valori:' t []

Matrice di valori da campionare.



## <a name="output--t"></a>Output:' t []

Matrice di elementi dai valori, in base alla pianificazione specificata.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Sampled (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854939"
---
# <a name="sampled-function"></a>Sampled (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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


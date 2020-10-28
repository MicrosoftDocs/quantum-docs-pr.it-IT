---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operazione TrainSequentialClassifierAtModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: b9e30e4e5bc23f56d9119083045967caff28f13a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720459"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>Operazione TrainSequentialClassifierAtModel

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Data la struttura di un classificatore sequenziale, addestra il classificatore su un set di training con etichetta specificato, a partire da un modello particolare.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Input

### <a name="model--sequentialmodel"></a>Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modello sequenziale da utilizzare come punto di partenza per il training.


### <a name="samples--labeledsample"></a>Esempi: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Set di dati di training con etichette che verranno utilizzati per eseguire il training.


### <a name="options--trainingoptions"></a>opzioni: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Configurazione da usare durante il training; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" per ulteriori informazioni, vedere e.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Pianificazione di campionamento da usare quando si selezionano esempi dai dati di training durante i passaggi di training.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Pianificazione di campionamento da usare quando si selezionano esempi dai dati di training quando si seleziona il punto iniziale che ha determinato il Punteggio di classificazione migliore.



## <a name="output--sequentialmodelint"></a>Output: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- Parametrizzazione del classificatore specificato e distorsione tra le due classi, insieme corrispondenti al risultato migliore da ognuno dei punti di inizio specificati.
- Numero di mancati riscontri osservati nel modello di classificazione migliore.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operazione TrainSequentialClassifierAtModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857148"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>Operazione TrainSequentialClassifierAtModel

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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
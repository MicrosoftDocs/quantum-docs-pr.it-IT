---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Tipo definito dall'utente TrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842773"
---
# <a name="trainingoptions-user-defined-type"></a>Tipo definito dall'utente TrainingOptions

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Raccolta di opzioni da utilizzare per i classificatori Quantum di training.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Elementi denominati

### <a name="learningrate--double"></a>LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)

Velocità di apprendimento in base alla quale è necessario ridimensionare le sfumature quando si aggiornano i parametri del modello durante i passaggi di training.
### <a name="tolerance--double"></a>Tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

La tolleranza di approssimazione da usare quando si preparano campioni come stati Quantum.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Numero di campioni da usare in ogni minibatch di training.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui misurare ogni risultato della classificazione per stimare la probabilità di classificazione.
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Numero massimo di epoche per il training di ogni modello.
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

Il numero massimo di volte in cui è consentita l'esecuzione di un periodo di training, ovvero una sfumatura di circa zero, prima dell'errore
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)

Quantità di ridimensionare i modelli bloccati da prima di ritentare un aggiornamento.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

Numero di passaggi sfumatura da intraprendere tra i punti di punteggio.
Per un'accuratezza ottimale, impostare su 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [](xref:microsoft.quantum.lang-ref.string) -> [unità](xref:microsoft.quantum.lang-ref.unit) di stringa

Funzione che può essere utilizzata per fornire commenti e suggerimenti dettagliati.

## <a name="remarks"></a>Commenti

Questo tipo definito dall'utente non deve essere creato direttamente, bensì deve essere specificato chiamando @"microsoft.quantum.machinelearning.defaulttrainingoptions" e quindi usando l' `w/` operatore per eseguire l'override di impostazioni predefinite diverse.

Ad esempio, per usare misure 100.000 e al massimo 8 epoche di training:

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Riferimenti

- [arXiv: 1804.00633](https://arxiv.org/abs/1804.00633)
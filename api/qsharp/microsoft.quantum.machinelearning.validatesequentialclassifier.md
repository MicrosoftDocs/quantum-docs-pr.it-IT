---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Operazione ValidateSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720447"
---
# <a name="validatesequentialclassifier-operation"></a>Operazione ValidateSequentialClassifier

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Convalida un classificatore sequenziale specificato rispetto a un determinato set di campioni con etichette precedenti.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Input

### <a name="model--sequentialmodel"></a>Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modello sequenziale da convalidare.


### <a name="samples--labeledsample"></a>Esempi: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Esempi da utilizzare per convalidare il modello specificato.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza di approssimazione da utilizzare per la codifica di ogni campione come input per il classificatore sequenziale.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per la classificazione di ogni campione.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Pianificazione mediante la quale è necessario disegnare gli esempi dal set di convalida.



## <a name="output--validationresults"></a>Output: [validationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Risultati della convalida specificata.
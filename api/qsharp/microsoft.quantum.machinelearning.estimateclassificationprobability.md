---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operazione EstimateClassificationProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196464"
---
# <a name="estimateclassificationprobability-operation"></a>Operazione EstimateClassificationProbability

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dato un esempio e un classificatore sequenziale, stima la probabilità di classificazione per l'esempio misurando ripetutamente l'output del classificatore sull'esempio specificato.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.


### <a name="model--sequentialmodel"></a>Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modello sequenziale da utilizzare per stimare la probabilità di classificazione per l'esempio specificato.


### <a name="sample--double"></a>esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di funzionalità per l'esempio da classificare.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Stima della probabilità di classificazione per l'esempio specificato.
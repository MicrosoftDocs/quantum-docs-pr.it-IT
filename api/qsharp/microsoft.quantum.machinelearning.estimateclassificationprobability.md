---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operazione EstimateClassificationProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853951"
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
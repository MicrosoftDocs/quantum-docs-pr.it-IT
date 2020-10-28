---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operazione EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709775"
---
# <a name="estimateclassificationprobability-operation"></a>Operazione EstimateClassificationProbability

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


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
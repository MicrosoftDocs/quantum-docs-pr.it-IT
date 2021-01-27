---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operazione EstimateClassificationProbabilities
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847729"
---
# <a name="estimateclassificationprobabilities-operation"></a>Operazione EstimateClassificationProbabilities

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dato un set di esempi e un classificatore sequenziale, in viene stimata la probabilità di classificazione per tali campioni, misurando ripetutamente l'output del classificatore su ciascun campione.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza che consente di codificare l'esempio in un'operazione di preparazione dello stato.


### <a name="model--sequentialmodel"></a>Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modello sequenziale da utilizzare per stimare le probabilità di classificazione per gli esempi specificati.


### <a name="samples--double"></a>Esempi: [Double](xref:microsoft.quantum.lang-ref.double)[] []

Matrice di vettori di funzionalità per ogni campione da classificare.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la probabilità di classificazione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di stime della probabilità di classificazione per ogni esempio specificato.
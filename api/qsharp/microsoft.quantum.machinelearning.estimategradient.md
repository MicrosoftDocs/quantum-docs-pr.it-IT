---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operazione EstimateGradient
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211849"
---
# <a name="estimategradient-operation"></a>Operazione EstimateGradient

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Stima la sfumatura di training per un classificatore sequenziale in un modello specifico e per un input codificato specificato.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Input

### <a name="model--sequentialmodel"></a>Modello: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modello sequenziale di cui è necessario stimare la sfumatura.


### <a name="encodedinput--stategenerator"></a>encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Input per il classificatore sequenziale, codificato in un'operazione di preparazione dello stato.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la sfumatura.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)[]

Stima della sfumatura di training ai parametri di input e di modello specificati.

## <a name="remarks"></a>Commenti

Questa operazione usa un test Hadamard e la tecnica Shift del parametro insieme per stimare la sfumatura.
---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definito dall'utente SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196175"
---
# <a name="sequentialmodel-user-defined-type"></a>Tipo definito dall'utente SequentialModel

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Descrive un modello di classificazione quantistica costituito da una sequenza di rotazioni con parametri e controllate, da un'assegnazione di angoli di rotazione e da una distorsione tra le due classi riconosciute dal modello.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Elementi denominati

### <a name="structure--controlledrotation"></a>Struttura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Sequenza di rotazioni controllate utilizzate per classificare gli input.
### <a name="parameters--double"></a>Parametri: [Double](xref:microsoft.quantum.lang-ref.double)[]

Assegnazione degli angoli di rotazione alla struttura di classificazione specificata.
### <a name="bias--double"></a>Distorsione: [Double](xref:microsoft.quantum.lang-ref.double)

Distorsione tra le due classi riconosciute da questo classificatore.

## <a name="references"></a>Riferimenti

- [arXiv: 1804.00633](https://arxiv.org/abs/1804.00633)
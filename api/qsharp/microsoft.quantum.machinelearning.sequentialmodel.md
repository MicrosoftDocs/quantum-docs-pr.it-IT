---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definito dall'utente SequentialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854903"
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
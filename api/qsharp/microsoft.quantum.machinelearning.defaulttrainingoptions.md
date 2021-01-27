---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855998"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Restituisce un set predefinito di opzioni per i classificatori di training.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Output: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Set ragionevole di opzioni di training predefinite da utilizzare per i classificatori di training.

## <a name="example"></a>Esempio

Per usare le opzioni predefinite, ma con misurazioni aggiuntive, usare l' `w/` operatore:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```
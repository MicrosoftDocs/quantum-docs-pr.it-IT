---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definito dall'utente LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196328"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definito dall'utente LabeledSample

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Esempio, etichettato con una classe a cui appartiene l'esempio.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="features--double"></a>Funzionalità: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di funzionalità per l'esempio specificato.
### <a name="label--int"></a>Etichetta: [int](xref:microsoft.quantum.lang-ref.int)

Etichetta integer per la classe a cui appartiene l'esempio.
---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definito dall'utente LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846969"
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
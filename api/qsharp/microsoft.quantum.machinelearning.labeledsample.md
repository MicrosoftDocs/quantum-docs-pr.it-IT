---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definito dall'utente LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711332"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definito dall'utente LabeledSample

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Esempio, etichettato con una classe a cui appartiene l'esempio.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="features--double"></a>Funzionalità: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di funzionalità per l'esempio specificato.
### <a name="label--int"></a>Etichetta: [int](xref:microsoft.quantum.lang-ref.int)

Etichetta integer per la classe a cui appartiene l'esempio.
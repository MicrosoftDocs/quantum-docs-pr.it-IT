---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Tipo definito dall'utente ValidationResults
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720426"
---
# <a name="validationresults-user-defined-type"></a>Tipo definito dall'utente ValidationResults

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Risultato della convalida di un classificatore rispetto a un set di campioni.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="nmisclassifications--int"></a>NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)

Numero di classificazioni errate osservate durante la convalida.
### <a name="nvalidationsamples--int"></a>NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)


---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196413"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Restituisce il numero di qubits necessari per codificare un vettore di funzionalità specifico.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Input

### <a name="sample--double"></a>esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di funzionalità di esempio da codificare in un registro qubit.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Dimensioni necessarie per codificare `sample` in un registro qubit, espresse come numero di qubits.
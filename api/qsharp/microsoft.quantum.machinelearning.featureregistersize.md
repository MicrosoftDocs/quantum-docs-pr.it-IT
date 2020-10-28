---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723289"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Restituisce il numero di qubits necessari per codificare un vettore di funzionalità specifico.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Input

### <a name="sample--double"></a>esempio: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di funzionalità di esempio da codificare in un registro qubit.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Dimensioni necessarie per codificare `sample` in un registro qubit, espresse come numero di qubits.
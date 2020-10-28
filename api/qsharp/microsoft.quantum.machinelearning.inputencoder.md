---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709750"
---
# <a name="inputencoder-function"></a>InputEncoder (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Dato un set di coefficienti e una tolleranza, restituisce un'operazione di preparazione dello stato che prepara ogni coefficiente come l'ampiezza corrispondente di uno stato di base computazionale.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Input

### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti da codificare in uno stato di input.



## <a name="output--stategenerator"></a>Output: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operazione di preparazione dello stato che prepara i coefficienti specificati come stato di input in un determinato registro.
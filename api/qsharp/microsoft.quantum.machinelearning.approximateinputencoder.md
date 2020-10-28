---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720534"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto [](https://nuget.org/packages/)


Dato un set di coefficienti e una tolleranza, restituisce un'operazione di preparazione dello stato che prepara ogni coefficiente come l'ampiezza corrispondente di uno stato di base computazionale, fino alla tolleranza specificata.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Input

### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza di approssimazione da utilizzare per la codifica dei coefficienti specificati in uno stato di input.


### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti da codificare in uno stato di input.



## <a name="output--stategenerator"></a>Output: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operazione di preparazione dello stato che prepara i coefficienti specificati come stato di input in un determinato registro.
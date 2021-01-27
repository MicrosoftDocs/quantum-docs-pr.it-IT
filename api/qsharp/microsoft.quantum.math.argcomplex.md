---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842767"
---
# <a name="argcomplex-function"></a>ArgComplex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce la fase di un numero complesso di tipo `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Input

### <a name="input--complex"></a>input: [complesso](xref:Microsoft.Quantum.Math.Complex)

Numero complesso $c = x + i y $.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Fase $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\Pi, \Pi] $.
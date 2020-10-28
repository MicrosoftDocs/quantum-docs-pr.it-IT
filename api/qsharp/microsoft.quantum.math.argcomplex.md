---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723264"
---
# <a name="argcomplex-function"></a>ArgComplex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Restituisce la fase di un numero complesso di tipo `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Input

### <a name="input--complex"></a>input: [complesso](xref:Microsoft.Quantum.Math.Complex)

Numero complesso $c = x + i y $.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Fase $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\Pi, \Pi] $.
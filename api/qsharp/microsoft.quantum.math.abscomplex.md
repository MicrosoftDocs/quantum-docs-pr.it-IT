---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211390"
---
# <a name="abscomplex-function"></a>AbsComplex (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce il valore assoluto di un numero complesso di tipo `Complex` .

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Input

### <a name="input--complex"></a>input: [complesso](xref:Microsoft.Quantum.Math.Complex)

Numero complesso $c = x + i y $.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Valore assoluto $ | c | = \sqrt{x ^ 2 + y ^ 2} $.
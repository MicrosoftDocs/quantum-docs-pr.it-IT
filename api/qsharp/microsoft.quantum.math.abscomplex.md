---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846077"
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
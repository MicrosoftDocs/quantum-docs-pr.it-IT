---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operazione EvaluatePolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843215"
---
# <a name="evaluatepolynomialfxp-operation"></a>Operazione EvaluatePolynomialFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Valuta un polinomiale in una rappresentazione a virgola fissa.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti del polinomi come una doppia matrice, ad esempio, la matrice $ [a_0, a_1,..., a_d] $ per la $P polinomiale (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di input per il quale valutare il polinomiale.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di output che conterrà $P (x) $. Deve trovarsi inizialmente in stato $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operazione EvaluatePolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721182"
---
# <a name="evaluatepolynomialfxp-operation"></a>Operazione EvaluatePolynomialFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Valuta un polinomiale in una rappresentazione a virgola fissa.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Input

### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti del polinomi come una doppia matrice, ad esempio, la matrice $ [a_0, a_1,..., a_d] $ per la $P polinomiale (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di input per il quale valutare il polinomiale.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di output che conterrà $P (x) $. Deve trovarsi inizialmente in stato $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

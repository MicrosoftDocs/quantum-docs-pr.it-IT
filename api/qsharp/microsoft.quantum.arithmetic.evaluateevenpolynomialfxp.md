---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Operazione EvaluateEvenPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721203"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>Operazione EvaluateEvenPolynomialFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Valuta un polinomio uniforme in una rappresentazione a virgola fissa.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Input

### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti del polinomio uniforme come una matrice doppia, ovvero la matrice $ [a_0, a_1,..., a_k] $ per la $P polinomiale (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2K} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di input per il quale valutare il polinomiale.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa di output che conterrà $P (x) $. Deve trovarsi inizialmente in stato $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


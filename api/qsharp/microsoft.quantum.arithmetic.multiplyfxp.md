---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operazione MultiplyFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843042"
---
# <a name="multiplyfxp-operation"></a>Operazione MultiplyFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Moltiplica due numeri a virgola fissa nei registri Quantum.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primo numero a virgola fissa.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Secondo numero a virgola fissa.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Il numero a virgola fissa risultato deve trovarsi nello stato $ \ket {0} $ inizialmente.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Per l'implementazione corrente è necessario che i tre numeri a virgola fissa abbiano la stessa posizione del punto e lo stesso numero di qubits.
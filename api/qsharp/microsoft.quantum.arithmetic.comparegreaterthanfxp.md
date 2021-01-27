---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operazione CompareGreaterThanFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843316"
---
# <a name="comparegreaterthanfxp-operation"></a>Operazione CompareGreaterThanFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Confronta due numeri a virgola fissa archiviati in registri Quantum e controlla un capovolgimento sul risultato.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primo numero a virgola fissa da confrontare.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Secondo numero a virgola fissa da confrontare.


### <a name="result--qubit"></a>risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Risultato del confronto. Verrà capovolto se `fp1 > fp2` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Per l'implementazione corrente è necessario che i due numeri a virgola fissa abbiano la stessa posizione del punto e lo stesso numero di qubits.
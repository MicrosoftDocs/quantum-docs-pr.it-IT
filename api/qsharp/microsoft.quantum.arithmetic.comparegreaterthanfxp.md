---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operazione CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721299"
---
# <a name="comparegreaterthanfxp-operation"></a>Operazione CompareGreaterThanFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Confronta due numeri a virgola fissa archiviati in registri Quantum e controlla un capovolgimento sul risultato.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
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
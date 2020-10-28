---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operazione ComputeReciprocalFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721251"
---
# <a name="computereciprocalfxp-operation"></a>Operazione ComputeReciprocalFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Calcola $1/x $ per un numero a virgola fissa $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Input

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa da invertire.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa che conterrà il risultato. Deve essere inizializzato su $ \ket{0.0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


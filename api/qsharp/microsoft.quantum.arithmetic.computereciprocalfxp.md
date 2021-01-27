---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operazione ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843256"
---
# <a name="computereciprocalfxp-operation"></a>Operazione ComputeReciprocalFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Calcola $1/x $ per un numero a virgola fissa $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa da invertire.


### <a name="result--fixedpoint"></a>risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numero a virgola fissa che conterrà il risultato. Deve essere inizializzato su $ \ket{0.0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


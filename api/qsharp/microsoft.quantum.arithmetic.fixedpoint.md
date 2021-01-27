---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definito dall'utente di FixedPoint
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843193"
---
# <a name="fixedpoint-user-defined-type"></a>Tipo definito dall'utente di FixedPoint

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Rappresenta un registro di qubits che codifica un numero a virgola fissa. È costituito da un numero intero uguale al numero di qubits a sinistra del punto binario, ad esempio, qubits di peso maggiore o uguale a 1 e un registro Quantum.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```


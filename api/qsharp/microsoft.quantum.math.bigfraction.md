---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definito dall'utente BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211084"
---
# <a name="bigfraction-user-defined-type"></a>Tipo definito dall'utente BigFraction

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un numero razionale del form `p/q` . Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Elementi denominati

### <a name="numerator--bigint"></a>Numeratore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numeratore della frazione.
### <a name="denominator--bigint"></a>Denominatore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Denominatore della frazione/
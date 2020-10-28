---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definito dall'utente BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723208"
---
# <a name="bigfraction-user-defined-type"></a>Tipo definito dall'utente BigFraction

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un numero razionale del form `p/q` . Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Elementi denominati

### <a name="numerator--bigint"></a>Numeratore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numeratore della frazione.
### <a name="denominator--bigint"></a>Denominatore: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Denominatore della frazione/
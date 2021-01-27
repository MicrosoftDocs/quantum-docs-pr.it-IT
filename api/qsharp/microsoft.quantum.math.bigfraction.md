---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definito dall'utente BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846913"
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
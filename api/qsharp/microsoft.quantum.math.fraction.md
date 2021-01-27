---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definito dall'utente
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857510"
---
# <a name="fraction-user-defined-type"></a>Tipo definito dall'utente

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un numero razionale del form `p/q` . Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="numerator--int"></a>Numeratore: [int](xref:microsoft.quantum.lang-ref.int)

Numeratore della frazione.
### <a name="denominator--int"></a>Denominatore: [int](xref:microsoft.quantum.lang-ref.int)

Denominatore della frazione/
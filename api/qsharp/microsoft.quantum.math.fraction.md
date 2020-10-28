---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definito dall'utente
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723656"
---
# <a name="fraction-user-defined-type"></a>Tipo definito dall'utente

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un numero razionale del form `p/q` . Integer `p` è il primo elemento della tupla ed `q` è il secondo elemento della tupla.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="numerator--int"></a>Numeratore: [int](xref:microsoft.quantum.lang-ref.int)

Numeratore della frazione.
### <a name="denominator--int"></a>Denominatore: [int](xref:microsoft.quantum.lang-ref.int)

Denominatore della frazione/
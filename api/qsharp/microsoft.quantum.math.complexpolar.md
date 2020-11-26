---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definito dall'utente ComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210982"
---
# <a name="complexpolar-user-defined-type"></a>Tipo definito dall'utente ComplexPolar

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un numero complesso in formato polare.

La rappresentazione polare di un numero complesso è $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Elementi denominati

### <a name="magnitude--double"></a>Magnitude: [Double](xref:microsoft.quantum.lang-ref.double)

Il valore assoluto $r \ge $0 di $c $.
### <a name="argument--double"></a>Argomento: [Double](xref:microsoft.quantum.lang-ref.double)

La fase $t \in \mathbb R $ di $c $.
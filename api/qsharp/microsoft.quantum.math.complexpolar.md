---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definito dall'utente ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847339"
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
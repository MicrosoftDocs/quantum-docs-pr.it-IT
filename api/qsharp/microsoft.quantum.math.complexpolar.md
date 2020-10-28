---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definito dall'utente ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709649"
---
# <a name="complexpolar-user-defined-type"></a>Tipo definito dall'utente ComplexPolar

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


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
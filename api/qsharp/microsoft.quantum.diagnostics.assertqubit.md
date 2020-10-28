---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operazione AssertQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712942"
---
# <a name="assertqubit-operation"></a>Operazione AssertQubit

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Asserisce che qubit `q` si trova nel autostato previsto dell'operatore Pauli Z.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="expected--__invalidresult__"></a>previsto: __non <Result> valido__

Stato in cui si prevede che il qubit sia in: `Zero` o `One` .


### <a name="q--qubit"></a>d: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di cui viene dichiarato lo stato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> consente di dichiarare gli Stati qubit arbitrari anziché solo $Z $ autostati.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)
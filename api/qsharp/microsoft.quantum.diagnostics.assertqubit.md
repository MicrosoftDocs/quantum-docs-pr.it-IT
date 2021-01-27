---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operazione AssertQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853446"
---
# <a name="assertqubit-operation"></a>Operazione AssertQubit

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
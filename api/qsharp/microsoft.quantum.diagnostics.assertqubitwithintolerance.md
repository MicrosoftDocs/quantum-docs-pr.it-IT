---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operazione AssertQubitWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853428"
---
# <a name="assertqubitwithintolerance-operation"></a>Operazione AssertQubitWithinTolerance

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Asserisce che qubit `q` si trova nel autostato previsto dell'operatore Pauli Z fino a una determinata tolleranza.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Input

### <a name="expected--__invalidresult__"></a>previsto: __non <Result> valido__

Stato in cui si prevede che il qubit sia in: `Zero` o `One` .


### <a name="q--qubit"></a>d: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di cui viene dichiarato lo stato.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza sulla probabilità di una misurazione di qubit che restituisce il risultato previsto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> consente di dichiarare gli Stati qubit arbitrari anziché solo $Z $ autostati.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)
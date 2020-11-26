---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operazione AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202261"
---
# <a name="assertphase-operation"></a>Operazione AssertPhase

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Asserisce che la fase di uno stato di sovrapposizione uguale presenta il valore previsto.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione asserisce che la fase $ \Phi $ di uno stato quantum che può essere espressa come $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ per un $t reale arbitrario $ ha il valore previsto.

## <a name="input"></a>Input

### <a name="expected--double"></a>previsto: [Double](xref:microsoft.quantum.lang-ref.double)

Il valore previsto di $ \Phi \In (-\Pi, \Pi] $.


### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit che archivia lo stato previsto.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


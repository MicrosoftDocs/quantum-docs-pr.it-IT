---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operazione AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830072"
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



## <a name="example"></a>Esempio

L'asserzione seguente ha esito positivo: `qubit` è nello stato $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {i 0.5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` è nello stato $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0.5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` è nello stato $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ KET {0} + e ^ {i 0.2} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`
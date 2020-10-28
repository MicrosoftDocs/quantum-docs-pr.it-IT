---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operazione AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721362"
---
# <a name="assertprobint-operation"></a>Operazione AssertProbInt

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Asserisce che la probabilità di uno stato specifico di un registro Quantum presenta il valore previsto.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Descrizione

Dato un $n $-qubit quantum state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, asserisce che la probabilità $ | \ alpha_j | ^ 2 $ dello stato $ \ket{j} $ indicizzato da $j $ presenta il valore previsto.

## <a name="input"></a>Input

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indice $j $ dello stato $ \ket{j} $ rappresentato da un `LittleEndian` registro.


### <a name="expected--double"></a>previsto: [Double](xref:microsoft.quantum.lang-ref.double)

Il valore previsto di $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro qubit che archivia $ \ket{\psi} $ in formato little-endian.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


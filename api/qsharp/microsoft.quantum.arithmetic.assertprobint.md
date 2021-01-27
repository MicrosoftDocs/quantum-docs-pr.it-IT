---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operazione AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843413"
---
# <a name="assertprobint-operation"></a>Operazione AssertProbInt

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Esempio

Si supponga che il `qubits` registro codifichi uno stato quantum 3-qubit $ \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {6} $ in formato little-endian.
Ciò significa che il numero indica $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ e $ \ket {6} \equiv\ket \ket \ket {0} {1} {1} $. Quindi, le asserzioni seguenti hanno esito positivo:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```
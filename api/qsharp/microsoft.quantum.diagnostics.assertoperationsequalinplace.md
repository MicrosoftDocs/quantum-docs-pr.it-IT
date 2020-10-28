---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operazione AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712970"
---
# <a name="assertoperationsequalinplace-operation"></a>Operazione AssertOperationsEqualInPlace

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Date due operazioni, asserisce che agiscono in modo identico per tutti gli Stati di input.

Questa asserzione viene implementata controllando l'azione delle operazioni su tutti gli Stati nel formato $V _0 \otimes... \otimes V_ {n-1} $, dove $V _k $ è uno degli Stati $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ e $ \ket{i} $ (+ 1 autostato dell'operatore Pauli Y).

Questa asserzione USA $n $ qubits e richiede il confronto di più chiamate delle operazioni.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di qubits $n $ `givenU` su cui operano le operazioni e `expectedU` .


### <a name="givenu--qubit--unit"></a>dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione su $n $ qubits da controllare.


### <a name="expectedu--qubit--unit-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione di riferimento su $n $ qubits da `givenU` confrontare con.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

La base degli Stati $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ e $ \ket{i} $ è la Chuang-Nielsen, descritta in [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)
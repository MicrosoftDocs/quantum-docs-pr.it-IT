---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operazione PrepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854371"
---
# <a name="prepareentangledstate-operation"></a>Operazione PrepareEntangledState

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pairwise si impiglia in due registri qubit.

Ovvero, dati due registri, prepara lo stato {1} di \frac {\sqrt {2} } \left (\ket {00} + \ket {11} \right) di ogni coppia di qubits sui rispettivi registri, supponendo che ogni registro venga avviato nello stato $ \ket{0\cdots 0} $.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


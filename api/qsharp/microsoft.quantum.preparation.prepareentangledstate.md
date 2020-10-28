---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operazione PrepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722172"
---
# <a name="prepareentangledstate-operation"></a>Operazione PrepareEntangledState

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Pairwise si impiglia in due registri qubit.

Ovvero, dati due registri, prepara lo stato {1} di \frac {\sqrt {2} } \left (\ket {00} + \ket {11} \right) di ogni coppia di qubits sui rispettivi registri, supponendo che ogni registro venga avviato nello stato $ \ket{0\cdots 0} $.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


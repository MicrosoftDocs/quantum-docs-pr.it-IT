---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operazione _prepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713135"
---
# <a name="_prepareentangledstate-operation"></a>operazione _prepareEntangledState

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Dato due registri, prepara lo stato con la massima correlazione tra ogni coppia di qubits nei rispettivi registri.
Tutti i qubits devono iniziare nello stato di ⟩ | 0.

Il risultato è che le coppie corrispondenti di qubits da ogni registro si trovano in $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit nello stato $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


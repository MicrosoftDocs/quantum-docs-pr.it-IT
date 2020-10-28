---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operazione ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718362"
---
# <a name="applycnotchainwithtarget-operation"></a>Operazione ApplyCNOTChainWithTarget

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Calcola la parità di una matrice di qubits in un qubit di destinazione.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Se la matrice è inizialmente nello stato $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{target}}} $, lo stato finale viene fornito da $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{target}}} $.

## <a name="input"></a>Input

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice di qubits in cui viene calcolata la parità.


### <a name="targetqubit--qubit"></a>targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit finale in cui la parità di ' qubits ' è XORed.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

e

```qsharp
ApplyCNOTChain(qs);
```
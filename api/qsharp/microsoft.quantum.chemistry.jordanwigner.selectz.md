---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operazione SelectZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224718"
---
# <a name="selectz-operation"></a>Operazione SelectZ

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Un Unity $U $ che applica Pauli $Z $ Gate in una qubits $p $ conditioned in uno stato di indice $ \ket{p} $. Ovvero $ $ \begin{align} U\ket {p} \ KET {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Lo stato $ \ket{p} $ di questo registro determina il qubit a cui viene applicato $Z $.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits a cui vengono applicati gli operatori Pauli.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Operazione ApplyToPartitionC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717114"
---
# <a name="applytopartitionc-operation"></a>Operazione ApplyToPartitionC

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una coppia di operazioni a una determinata partizione di un registro in due parti.
Il modificatore `C` indica che l'operazione è controllabile.

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubitqubit--unit-ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Coppia di operazioni da applicare alla partizione specificata.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits dalla destinazione da inserire nella prima parte della partizione.
I qubits rimanenti costituiscono la seconda parte della partizione.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits di cui è in corso il partizionamento e l'utilizzo da parte delle due operazioni specificate.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)
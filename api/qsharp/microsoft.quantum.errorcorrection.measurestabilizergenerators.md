---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operazione MeasureStabilizerGenerators
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825763"
---
# <a name="measurestabilizergenerators-operation"></a>Operazione MeasureStabilizerGenerators

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misura il set specificato di generatori di un gruppo stabilizzatore.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Input

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matrice di operatori multiqubit Pauli.
Ad esempio, `stabilizerGroup[0]` è un elenco di matrici Pauli Single-qubit, il prodotto tensore di che è un generatore di stabilizzatori.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Matrice di qubits in cui è definito il codice di stabilizzazione.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valido__ 

Operazione che specifica come misurare un operatore multiqubit Pauli.



## <a name="output--syndrome"></a>Output: [sindrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Risultato delle misurazioni.

## <a name="remarks"></a>Commenti

Questa operazione non controlla se il set specificato di generatori è in permuta.
Se non eseguono la permuta, il risultato delle misurazioni può essere arbitrario.
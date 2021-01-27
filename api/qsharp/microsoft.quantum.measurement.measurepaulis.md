---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operazione MeasurePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853776"
---
# <a name="measurepaulis-operation"></a>Operazione MeasurePaulis

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice di operatori qubit di Pauli, misura ognuno usando un gadget di misurazione specificato, quindi restituisce la matrice di risultati.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matrice di operatori Pauli multiqubit da misurare.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per misurare gli operatori specificati.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valido__ 

Operazione che esegue la misurazione di un operatore multiqubit specificato.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__[]

Matrice di risultati ottenuti dalla misurazione di ogni elemento di `paulis` su `target` .
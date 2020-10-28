---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operazione MeasurePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720342"
---
# <a name="measurepaulis-operation"></a>Operazione MeasurePaulis

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di operatori qubit di Pauli, misura ognuno usando un gadget di misurazione specificato, quindi restituisce la matrice di risultati.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matrice di operatori Pauli multiqubit da misurare.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per misurare gli operatori specificati.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valido__ 

Operazione che esegue la misurazione di un operatore multiqubit specificato.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__ []

Matrice di risultati ottenuti dalla misurazione di ogni elemento di `paulis` su `target` .
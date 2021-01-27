---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operazione MeasureWithScratch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854652"
---
# <a name="measurewithscratch-operation"></a>Operazione MeasureWithScratch

Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misura l'operatore Pauli specificato usando un qubit di Scratch esplicito per eseguire la misurazione.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un operatore Pauli multiqubit specificato come una matrice di operatori Pauli a qubit singolo.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato della misurazione dell'operatore Pauli specificato nel `target` registro.
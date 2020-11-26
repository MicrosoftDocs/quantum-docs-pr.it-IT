---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Operazione EstimateRealOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: d9f569ceffc16f377189dc94035213b9075609cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216184"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>Operazione EstimateRealOverlapBetweenStates

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la parte reale della sovrapposizione tra gli stati preparati da ogni operazione.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Operazione che prepara uno stato di input fisso.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Prima delle due operazioni di preparazione dello stato da confrontare.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Secondo delle due operazioni di preparazione dello stato da confrontare.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la sovrapposizione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Questa operazione usa il test Hadamard per trovare la parte reale di $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ dove $ \ket{\psi} $ è lo stato preparato da `commonPreparation` , $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .

## <a name="references"></a>Riferimenti

- Aharonov *et al.* [quante-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Characteration. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft. Quantum. Characteration. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)
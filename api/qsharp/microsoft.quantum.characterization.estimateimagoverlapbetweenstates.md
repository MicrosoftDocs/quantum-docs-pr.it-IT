---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: Operazione EstimateImagOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 8b73115c3243c594897ac4b309ec52d5e9863d26
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715042"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>Operazione EstimateImagOverlapBetweenStates

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la parte immaginaria della sovrapposizione tra gli stati preparati da ogni operazione.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Operazione che prepara uno stato di input fisso.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Prima delle due operazioni di preparazione dello stato da confrontare.


### <a name="preparation2--qubit--unit-adj--ctl"></a>Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Secondo delle due operazioni di preparazione dello stato da confrontare.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la sovrapposizione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Questa operazione usa il test Hadamard per trovare la parte immaginaria di $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ dove $ \ket{\psi} $ è lo stato preparato da `commonPreparation` , $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .

## <a name="references"></a>Riferimenti

- Aharonov *et al.* [quante-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Characteration. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. Characteration. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)
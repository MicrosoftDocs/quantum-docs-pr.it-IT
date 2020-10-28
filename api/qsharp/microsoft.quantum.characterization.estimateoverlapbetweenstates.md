---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operazione EstimateOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714997"
---
# <a name="estimateoverlapbetweenstates-operation"></a>Operazione EstimateOverlapBetweenStates

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la sovrapposizione quadrata tra gli stati preparati da ogni operazione.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Input

### <a name="preparation1--qubit--unit-adj"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Prima delle due operazioni di preparazione dello stato da confrontare.


### <a name="preparation2--qubit--unit-adj"></a>Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

Secondo delle due operazioni di preparazione dello stato da confrontare.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Numero di misurazioni da utilizzare per stimare la sovrapposizione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Questa operazione usa il test di scambio per trovare $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $ where $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Characteration. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. Characteration. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operazione EstimateTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224650"
---
# <a name="estimatetermexpectation-operation"></a>Operazione EstimateTermExpectation

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcola l'energia associata a un determinato termine di Jordan-Wigner hamiltoniana

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Descrizione

Questa operazione consente di stimare il valore di previsione associato a ciascun operatore di misurazione e di moltiplicarlo per il coefficiente corrispondente usando il campionamento.
I risultati vengono aggregati in una variabile che contiene l'energia del termine Jordan-Wigner.

## <a name="input"></a>Input

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Unitario utilizzato per la preparazione dello stato.


### <a name="ops--pauli"></a>Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Operatori di misurazione del termine del Jordan-Wigner.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coefficienti del termine del Jordan-Wigner.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits necessari per simulare il sistema molecolare.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Numero di campioni da utilizzare per la stima del termine previsto.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Energia associata al termine Jordan-Wigner.
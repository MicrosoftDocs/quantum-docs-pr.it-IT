---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operazione EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713726"
---
# <a name="estimatetermexpectation-operation"></a>Operazione EstimateTermExpectation

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto [](https://nuget.org/packages/)


Calcola l'energia associata a un determinato termine di Jordan-Wigner hamiltoniana

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Descrizione

Questa operazione consente di stimare il valore di previsione associato a ciascun operatore di misurazione e di moltiplicarlo per il coefficiente corrispondente usando il campionamento.
I risultati vengono aggregati in una variabile che contiene l'energia del termine Jordan-Wigner.

## <a name="input"></a>Input

### <a name="inputstateunitary--qubit--unit-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ

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
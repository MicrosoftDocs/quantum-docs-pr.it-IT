---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: operazione _prepareTrialStateWrapper
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713765"
---
# <a name="_preparetrialstatewrapper-operation"></a>operazione _prepareTrialStateWrapper

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto [](https://nuget.org/packages/)


Wrapper privato intorno a PrepareTrialState per renderlo compatibile con EstimateFrequencyA definendo un contiguo.
EstimateFrequencyA offre funzionalità di emulazione incorporata quando la destinazione è la QuantumSimulator, che accelera l'esecuzione.

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="inputstate--intjordanwignerinputstate"></a>inputState: ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])

Input Jordan-Wigner necessario per l'esecuzione di PrepareTrialState.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro qubit.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operazione DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715070"
---
# <a name="discretephaseestimationiteration-operation"></a>Operazione DiscretePhaseEstimationIteration

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Esegue una singola iterazione di un algoritmo di stima della fase iterativo (controllo classico) usando le potenze di un numero intero di un Oracle unitario.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operazione che agisce su un numero intero e un registro, in modo che $U ^ m $ venga applicato al registro specificato, dove $U $ è l'unità di cui è necessario stimare la fase e dove $m $ è la potenza intera assegnata a Oracle


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Numero di volte in cui applicare l'oggetto Oracle unitario specificato.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Angolo in base al quale invertire la fase sul controllo qubit prima di agire sullo stato di destinazione.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro dello stato a cui si basa il Oracle unitario specificato.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ausiliario utilizzato per controllare l'applicazione del Oracle specificato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operazione ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715081"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operazione ContinuousPhaseEstimationIteration

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Esegue una singola iterazione di un algoritmo di stima della fase iterativo (controllo classico) utilizzando poteri reali arbitrari di un Oracle unitario.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operazione che agisce su un valore Double $t $ e un Register, in modo che $U ^ t $ venga applicato al registro specificato, dove $U $ è l'unità di cui è necessario stimare la fase e dove $t $ è la potenza Integer assegnata a Oracle


### <a name="time--double"></a>Ora: [Double](xref:microsoft.quantum.lang-ref.double)

Numero di volte in cui applicare l'oggetto Oracle unitario specificato.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Angolo in base al quale invertire la fase sul controllo qubit prima di agire sullo stato di destinazione.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro dello stato a cui si basa il Oracle unitario specificato.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operazione QuantumPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714944"
---
# <a name="quantumphaseestimation-operation"></a>Operazione QuantumPhaseEstimation

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Esegue l'algoritmo di stima della fase quantistica per un determinato Oracle `U` e `targetState` , leggendo la fase in un registro Quantum big-endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Input

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Un'operazione che implementa $U ^ m $ per dati Integer specificati m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro Quantum che rappresenta lo stato $ \ket{\Phi} $ agito da $U $. Se $ \ket{\Phi} $ è un autostato di $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ per $ \Phi \In [0, 2 \ PI) $ una fase sconosciuta.


### <a name="controlregister--bigendian"></a>controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registro Integer di rappresentazione big-endian che può essere utilizzato per controllare l'oggetto Oracle specificato e che conterrà la rappresentazione di $ \Phi $ dopo l'applicazione di questa operazione. Si presuppone che controlRegister si avvii nello stato iniziale $ \ket{00\cdots 0} $, dove la lunghezza del registro indica la precisione desiderata.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

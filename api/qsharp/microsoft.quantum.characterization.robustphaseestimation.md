---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operazione RobustPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851808"
---
# <a name="robustphaseestimation-operation"></a>Operazione RobustPhaseEstimation

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue il solido algoritmo di stima della fase quantum non iterativo per un determinato Oracle `U` e autostato e fornisce una singola stima con valore reale della fase con scalabilità della varianza al limite di Heisenberg.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Input

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

Questa operazione fornisce una stima di $ \Phi $ con deviazione standard $ \sigma \Le 2 \ PI/2 ^ \text{bitsPrecision} $ usando una serie di query che si ridimensionano come $ \sigma \Le 10,7 \Pi/\Text{# of Queries} $.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Un'operazione che implementa $U ^ m $ per le potenze Integer date $m $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro Quantum su cui $U $ agisce. Se archivia un autostato $ \ket{\Phi} $ di $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ per $ \phi\in (-\Pi, \Pi] $ una fase sconosciuta.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Nel limite di un numero elevato di query, Cramer-Rao limiti inferiori per la deviazione standard della stima di $ \Phi $ soddisfino $ \sigma \ge 2 \Pi/\Text{# of Queries} $.

## <a name="references"></a>Riferimenti

- Taratura affidabile di un Single-Qubit universale Gate-Set tramite una valutazione della fase affidabile Shelby Kimmel, Guang Hao low, Theodore J. Yoder https://arxiv.org/abs/1502.02677
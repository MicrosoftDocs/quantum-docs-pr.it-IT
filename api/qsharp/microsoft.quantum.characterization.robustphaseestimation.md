---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operazione RobustPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714941"
---
# <a name="robustphaseestimation-operation"></a>Operazione RobustPhaseEstimation

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


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
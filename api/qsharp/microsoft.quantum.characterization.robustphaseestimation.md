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
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="fcdbf-102">Operazione RobustPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="fcdbf-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="fcdbf-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fcdbf-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="fcdbf-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcdbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcdbf-105">Esegue il solido algoritmo di stima della fase quantum non iterativo per un determinato Oracle `U` e autostato e fornisce una singola stima con valore reale della fase con scalabilità della varianza al limite di Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="fcdbf-106">Input</span><span class="sxs-lookup"><span data-stu-id="fcdbf-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="fcdbf-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcdbf-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcdbf-108">Questa operazione fornisce una stima di $ \Phi $ con deviazione standard $ \sigma \Le 2 \ PI/2 ^ \text{bitsPrecision} $ usando una serie di query che si ridimensionano come $ \sigma \Le 10,7 \Pi/\Text{# of Queries} $.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="fcdbf-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="fcdbf-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="fcdbf-110">Un'operazione che implementa $U ^ m $ per le potenze Integer date $m $.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="fcdbf-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcdbf-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcdbf-112">Registro Quantum su cui $U $ agisce.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="fcdbf-113">Se archivia un autostato $ \ket{\Phi} $ di $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ per $ \phi\in (-\Pi, \Pi] $ una fase sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="fcdbf-114">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcdbf-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="fcdbf-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="fcdbf-115">Remarks</span></span>

<span data-ttu-id="fcdbf-116">Nel limite di un numero elevato di query, Cramer-Rao limiti inferiori per la deviazione standard della stima di $ \Phi $ soddisfino $ \sigma \ge 2 \Pi/\Text{# of Queries} $.</span><span class="sxs-lookup"><span data-stu-id="fcdbf-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="fcdbf-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="fcdbf-117">References</span></span>

- <span data-ttu-id="fcdbf-118">Taratura affidabile di un Single-Qubit universale Gate-Set tramite una valutazione della fase affidabile Shelby Kimmel, Guang Hao low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="fcdbf-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>
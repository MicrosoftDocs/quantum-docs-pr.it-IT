---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operazione ApplyFixedPointAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191534"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="75025-102">Operazione ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="75025-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="75025-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="75025-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="75025-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75025-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75025-105">Algoritmo di amplificazione dell'ampiezza Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="75025-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="75025-106">Input</span><span class="sxs-lookup"><span data-stu-id="75025-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="75025-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="75025-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="75025-108">Oracle unitario che prepara lo stato di avvio.</span><span class="sxs-lookup"><span data-stu-id="75025-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="75025-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="75025-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="75025-110">Registro qubit</span><span class="sxs-lookup"><span data-stu-id="75025-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="75025-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75025-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="75025-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="75025-112">Remarks</span></span>

<span data-ttu-id="75025-113">StartQubits deve essere nello stato $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="75025-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="75025-114">Questa operazione esegue l'iterazione su una serie di query con potenze di $2 $ fino a quando non viene raggiunto il numero massimo di query o viene trovato lo stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="75025-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>
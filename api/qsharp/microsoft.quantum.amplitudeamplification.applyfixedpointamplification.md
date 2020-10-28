---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operazione ApplyFixedPointAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721906"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="4e9fe-102">Operazione ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="4e9fe-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="4e9fe-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4e9fe-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4e9fe-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e9fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e9fe-105">Algoritmo di amplificazione dell'ampiezza Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="4e9fe-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4e9fe-106">Input</span><span class="sxs-lookup"><span data-stu-id="4e9fe-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="4e9fe-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="4e9fe-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="4e9fe-108">Oracle unitario che prepara lo stato di avvio.</span><span class="sxs-lookup"><span data-stu-id="4e9fe-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="4e9fe-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4e9fe-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4e9fe-110">Registro qubit</span><span class="sxs-lookup"><span data-stu-id="4e9fe-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e9fe-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e9fe-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4e9fe-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="4e9fe-112">Remarks</span></span>

<span data-ttu-id="4e9fe-113">StartQubits deve essere nello stato $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4e9fe-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="4e9fe-114">Questa operazione esegue l'iterazione su una serie di query con potenze di $2 $ fino a quando non viene raggiunto il numero massimo di query o viene trovato lo stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4e9fe-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>
---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845813"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="ed6c5-102">ObliviousAmplitudeAmplificationFromStatePreparation (funzione)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="ed6c5-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ed6c5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed6c5-105">Amplificazione dell'ampiezza ignara da parte di Oracle per riflessioni parziali.</span><span class="sxs-lookup"><span data-stu-id="ed6c5-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ed6c5-106">Input</span><span class="sxs-lookup"><span data-stu-id="ed6c5-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="ed6c5-107">fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ed6c5-108">Fasi di riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="ed6c5-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="ed6c5-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="ed6c5-110">Oracle $A $ unitario che prepara lo stato di avvio ausiliario</span><span class="sxs-lookup"><span data-stu-id="ed6c5-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="ed6c5-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="ed6c5-112">Oracle $O $ di tipo `ObliviousOracle` che agisce congiuntamente sull'ausiliario e sul Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="ed6c5-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="ed6c5-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed6c5-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed6c5-114">Indice per il registro del flag Single-qubit</span><span class="sxs-lookup"><span data-stu-id="ed6c5-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="ed6c5-115">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ed6c5-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ed6c5-116">Operazione che implementa l'amplificazione dell'ampiezza ignara basata su riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="ed6c5-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed6c5-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="ed6c5-117">Remarks</span></span>

<span data-ttu-id="ed6c5-118">Questa operazione impone condizioni più restrittive sotto forma di Stati di avvio e di destinazione ausiliari rispetto a `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="ed6c5-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="ed6c5-119">Si presuppone che $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {fa} $ prepara lo stato di avvio ausiliario $ \ket{\Text{Start}} \_ {fa} $ dalla base computazionale $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="ed6c5-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="ed6c5-120">Si presuppone che lo stato di destinazione sia contrassegnato da $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="ed6c5-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="ed6c5-121">Si presuppone che \begin{align} O\ket {\ text {Start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {Any}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} per alcuni Unity $U $.</span><span class="sxs-lookup"><span data-stu-id="ed6c5-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>
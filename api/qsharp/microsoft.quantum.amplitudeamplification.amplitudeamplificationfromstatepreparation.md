---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721945"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="dadd9-102">AmplitudeAmplificationFromStatePreparation (funzione)</span><span class="sxs-lookup"><span data-stu-id="dadd9-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="dadd9-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="dadd9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="dadd9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dadd9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dadd9-105">Amplificazione dell'ampiezza da parte di Oracle per riflessioni parziali.</span><span class="sxs-lookup"><span data-stu-id="dadd9-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="dadd9-106">Input</span><span class="sxs-lookup"><span data-stu-id="dadd9-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="dadd9-107">fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="dadd9-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="dadd9-108">Fasi di riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="dadd9-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="dadd9-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="dadd9-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="dadd9-110">Oracle $A $ unitario che prepara lo stato di avvio</span><span class="sxs-lookup"><span data-stu-id="dadd9-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="dadd9-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dadd9-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dadd9-112">Indice per contrassegnare qubit</span><span class="sxs-lookup"><span data-stu-id="dadd9-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="dadd9-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dadd9-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="dadd9-114">Operazione che implementa l'amplificazione dell'ampiezza da parte di Oracle implementate da riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="dadd9-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="dadd9-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="dadd9-115">Remarks</span></span>

<span data-ttu-id="dadd9-116">Questa operazione impone condizioni più restrittive nel formato degli Stati di inizio e di destinazione rispetto a `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="dadd9-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="dadd9-117">Si presuppone che lo stato di destinazione sia contrassegnato da $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="dadd9-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="dadd9-118">Si presuppone che \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots {0} \_ , \end{align} nella maggior parte dei casi `flagQubit` e `auxiliaryRegister` siano inizializzati nello stato $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="dadd9-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>
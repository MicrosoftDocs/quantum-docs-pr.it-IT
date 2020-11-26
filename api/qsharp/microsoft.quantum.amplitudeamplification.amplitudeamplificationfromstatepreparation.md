---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191602"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="9952f-102">AmplitudeAmplificationFromStatePreparation (funzione)</span><span class="sxs-lookup"><span data-stu-id="9952f-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="9952f-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9952f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9952f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9952f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9952f-105">Amplificazione dell'ampiezza da parte di Oracle per riflessioni parziali.</span><span class="sxs-lookup"><span data-stu-id="9952f-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9952f-106">Input</span><span class="sxs-lookup"><span data-stu-id="9952f-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="9952f-107">fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="9952f-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="9952f-108">Fasi di riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="9952f-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="9952f-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="9952f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="9952f-110">Oracle $A $ unitario che prepara lo stato di avvio</span><span class="sxs-lookup"><span data-stu-id="9952f-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="9952f-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9952f-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9952f-112">Indice per contrassegnare qubit</span><span class="sxs-lookup"><span data-stu-id="9952f-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="9952f-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="9952f-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9952f-114">Operazione che implementa l'amplificazione dell'ampiezza da parte di Oracle implementate da riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="9952f-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="9952f-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9952f-115">Remarks</span></span>

<span data-ttu-id="9952f-116">Questa operazione impone condizioni più restrittive nel formato degli Stati di inizio e di destinazione rispetto a `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="9952f-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="9952f-117">Si presuppone che lo stato di destinazione sia contrassegnato da $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="9952f-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="9952f-118">Si presuppone che \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots {0} \_ , \end{align} nella maggior parte dei casi `flagQubit` e `auxiliaryRegister` siano inizializzati nello stato $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="9952f-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>
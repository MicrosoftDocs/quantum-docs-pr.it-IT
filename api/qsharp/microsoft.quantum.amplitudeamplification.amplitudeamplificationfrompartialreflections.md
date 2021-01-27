---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: e4030aabcab55db35bcb8199e37bee837ead6ad0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845906"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="dc524-102">AmplitudeAmplificationFromPartialReflections (funzione)</span><span class="sxs-lookup"><span data-stu-id="dc524-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="dc524-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="dc524-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="dc524-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc524-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc524-105">Amplificazione dell'ampiezza mediante riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="dc524-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="dc524-106">Input</span><span class="sxs-lookup"><span data-stu-id="dc524-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="dc524-107">fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="dc524-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="dc524-108">Fasi di riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="dc524-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="dc524-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="dc524-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="dc524-110">Operatore di Reflection sullo stato di avvio</span><span class="sxs-lookup"><span data-stu-id="dc524-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="dc524-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="dc524-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="dc524-112">Operatore di Reflection sullo stato di destinazione</span><span class="sxs-lookup"><span data-stu-id="dc524-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="dc524-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dc524-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dc524-114">Operazione che implementa l'amplificazione dell'ampiezza mediante riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="dc524-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc524-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="dc524-115">Remarks</span></span>

<span data-ttu-id="dc524-116">L'amplificazione dell'ampiezza è un caso speciale di amplificazione dell'ampiezza ignara in cui non sono presenti qubits di sistema e il Oracle ignaro è impostato su Identity.</span><span class="sxs-lookup"><span data-stu-id="dc524-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="dc524-117">Nella maggior parte dei casi, `startQubits` viene inizializzato nello stato $ \ket{\text{start}} \_ $1, ovvero $-$1 autostato di `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="dc524-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>
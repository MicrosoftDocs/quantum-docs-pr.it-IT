---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721948"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="3cc14-102">AmplitudeAmplificationFromPartialReflections (funzione)</span><span class="sxs-lookup"><span data-stu-id="3cc14-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="3cc14-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3cc14-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3cc14-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3cc14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3cc14-105">Amplificazione dell'ampiezza mediante riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="3cc14-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="3cc14-106">Input</span><span class="sxs-lookup"><span data-stu-id="3cc14-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="3cc14-107">fasi: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3cc14-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3cc14-108">Fasi di riflessioni parziali</span><span class="sxs-lookup"><span data-stu-id="3cc14-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="3cc14-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="3cc14-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="3cc14-110">Operatore di Reflection sullo stato di avvio</span><span class="sxs-lookup"><span data-stu-id="3cc14-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="3cc14-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="3cc14-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="3cc14-112">Operatore di Reflection sullo stato di destinazione</span><span class="sxs-lookup"><span data-stu-id="3cc14-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="3cc14-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3cc14-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3cc14-114">Operazione che implementa l'amplificazione dell'ampiezza mediante riflessi parziali.</span><span class="sxs-lookup"><span data-stu-id="3cc14-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cc14-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="3cc14-115">Remarks</span></span>

<span data-ttu-id="3cc14-116">L'amplificazione dell'ampiezza è un caso speciale di amplificazione dell'ampiezza ignara in cui non sono presenti qubits di sistema e il Oracle ignaro è impostato su Identity.</span><span class="sxs-lookup"><span data-stu-id="3cc14-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="3cc14-117">Nella maggior parte dei casi, `startQubits` viene inizializzato nello stato $ \ket{\text{start}} \_ $1, ovvero $-$1 autostato di `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="3cc14-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>
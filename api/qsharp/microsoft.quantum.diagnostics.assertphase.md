---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operazione AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202261"
---
# <a name="assertphase-operation"></a><span data-ttu-id="75a3b-102">Operazione AssertPhase</span><span class="sxs-lookup"><span data-stu-id="75a3b-102">AssertPhase operation</span></span>

<span data-ttu-id="75a3b-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="75a3b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="75a3b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75a3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75a3b-105">Asserisce che la fase di uno stato di sovrapposizione uguale presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="75a3b-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="75a3b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75a3b-106">Description</span></span>

<span data-ttu-id="75a3b-107">Questa operazione asserisce che la fase $ \Phi $ di uno stato quantum che può essere espressa come $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ per un $t reale arbitrario $ ha il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="75a3b-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="75a3b-108">Input</span><span class="sxs-lookup"><span data-stu-id="75a3b-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="75a3b-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75a3b-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75a3b-110">Il valore previsto di $ \Phi \In (-\Pi, \Pi] $.</span><span class="sxs-lookup"><span data-stu-id="75a3b-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="75a3b-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75a3b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75a3b-112">Qubit che archivia lo stato previsto.</span><span class="sxs-lookup"><span data-stu-id="75a3b-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="75a3b-113">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75a3b-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75a3b-114">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="75a3b-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75a3b-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75a3b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


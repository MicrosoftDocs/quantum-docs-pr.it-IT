---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operazione AssertPhase
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712953"
---
# <a name="assertphase-operation"></a><span data-ttu-id="a1cb4-102">Operazione AssertPhase</span><span class="sxs-lookup"><span data-stu-id="a1cb4-102">AssertPhase operation</span></span>

<span data-ttu-id="a1cb4-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a1cb4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1cb4-105">Asserisce che la fase di uno stato di sovrapposizione uguale presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="a1cb4-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="a1cb4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1cb4-106">Description</span></span>

<span data-ttu-id="a1cb4-107">Questa operazione asserisce che la fase $ \Phi $ di uno stato quantum che può essere espressa come $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ per un $t reale arbitrario $ ha il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="a1cb4-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="a1cb4-108">Input</span><span class="sxs-lookup"><span data-stu-id="a1cb4-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="a1cb4-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1cb4-110">Il valore previsto di $ \Phi \In (-\Pi, \Pi] $.</span><span class="sxs-lookup"><span data-stu-id="a1cb4-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a1cb4-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a1cb4-112">Qubit che archivia lo stato previsto.</span><span class="sxs-lookup"><span data-stu-id="a1cb4-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a1cb4-113">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1cb4-114">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="a1cb4-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1cb4-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1cb4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


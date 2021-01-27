---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operazione AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830072"
---
# <a name="assertphase-operation"></a><span data-ttu-id="67735-102">Operazione AssertPhase</span><span class="sxs-lookup"><span data-stu-id="67735-102">AssertPhase operation</span></span>

<span data-ttu-id="67735-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67735-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="67735-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67735-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67735-105">Asserisce che la fase di uno stato di sovrapposizione uguale presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="67735-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="67735-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67735-106">Description</span></span>

<span data-ttu-id="67735-107">Questa operazione asserisce che la fase $ \Phi $ di uno stato quantum che può essere espressa come $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ per un $t reale arbitrario $ ha il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="67735-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="67735-108">Input</span><span class="sxs-lookup"><span data-stu-id="67735-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="67735-109">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67735-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67735-110">Il valore previsto di $ \Phi \In (-\Pi, \Pi] $.</span><span class="sxs-lookup"><span data-stu-id="67735-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="67735-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="67735-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="67735-112">Qubit che archivia lo stato previsto.</span><span class="sxs-lookup"><span data-stu-id="67735-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="67735-113">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67735-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67735-114">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="67735-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67735-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67735-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="67735-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="67735-116">Example</span></span>

<span data-ttu-id="67735-117">L'asserzione seguente ha esito positivo: `qubit` è nello stato $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {i 0.5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="67735-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="67735-118">`qubit` è nello stato $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0.5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="67735-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="67735-119">`qubit` è nello stato $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ KET {0} + e ^ {i 0.2} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="67735-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`
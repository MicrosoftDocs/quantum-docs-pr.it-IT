---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848012"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="dbc9a-102">PauliBlockEncoding (funzione)</span><span class="sxs-lookup"><span data-stu-id="dbc9a-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="dbc9a-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dbc9a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dbc9a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbc9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbc9a-105">Crea un Unity di codifica a blocchi per un'Hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="dbc9a-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="dbc9a-106">Hamiltoniana $H = \ sum_ {j} \ alpha_j P_j $ è descritto da una somma dei termini di Pauli $P _j $, ognuno con un coefficiente reale $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="dbc9a-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="dbc9a-107">Input</span><span class="sxs-lookup"><span data-stu-id="dbc9a-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="dbc9a-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="dbc9a-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="dbc9a-109">Oggetto `GeneratorSystem` che descrive $H $ come somma dei termini di Pauli</span><span class="sxs-lookup"><span data-stu-id="dbc9a-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="dbc9a-110">Output: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="dbc9a-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="dbc9a-111">Primo parametro</span><span class="sxs-lookup"><span data-stu-id="dbc9a-111">First parameter</span></span>

<span data-ttu-id="dbc9a-112">La regola uno dei coefficienti $ \Alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="dbc9a-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="dbc9a-113">Secondo parametro</span><span class="sxs-lookup"><span data-stu-id="dbc9a-113">Second parameter</span></span>

<span data-ttu-id="dbc9a-114">`BlockEncodingReflection`Unitario $U $ dell'hamiltoniana $H $.</span><span class="sxs-lookup"><span data-stu-id="dbc9a-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="dbc9a-115">Poiché questo unitario soddisfa $U ^ 2 = I $, è anche una reflection.</span><span class="sxs-lookup"><span data-stu-id="dbc9a-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbc9a-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="dbc9a-116">Remarks</span></span>

<span data-ttu-id="dbc9a-117">Questa operazione viene ottenuta preparando e disinstallando lo stato $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ e costruendo un Unity controllato da moltiplicato <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="dbc9a-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>
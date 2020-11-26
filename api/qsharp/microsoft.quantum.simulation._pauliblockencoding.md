---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: Funzione _PauliBlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225568"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="f4ccd-102">Funzione _PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="f4ccd-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="f4ccd-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f4ccd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f4ccd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4ccd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4ccd-105">Crea un Unity di codifica a blocchi per un'Hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="f4ccd-106">Hamiltoniana $H = \ sum_ {j} \ alpha_j P_j $ è descritto da una somma dei termini di Pauli $P _j $, ognuno con un coefficiente reale $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="f4ccd-107">Input</span><span class="sxs-lookup"><span data-stu-id="f4ccd-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="f4ccd-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f4ccd-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f4ccd-109">Oggetto `GeneratorSystem` che descrive $H $ come somma dei termini di Pauli</span><span class="sxs-lookup"><span data-stu-id="f4ccd-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f4ccd-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f4ccd-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f4ccd-111">Un'operazione unitaria $V $ che applica il $V unitario _j $ controllato sull'indice $ \ket{j} $, data una funzione $f: j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="f4ccd-112">multiplexer: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unit](xref:microsoft.quantum.lang-ref.unit)  is ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unit](xref:microsoft.quantum.lang-ref.unit)  Is ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f4ccd-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="f4ccd-113">Output: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="f4ccd-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="f4ccd-114">Primo parametro</span><span class="sxs-lookup"><span data-stu-id="f4ccd-114">First parameter</span></span>

<span data-ttu-id="f4ccd-115">La regola uno dei coefficienti $ \Alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="f4ccd-116">Secondo parametro</span><span class="sxs-lookup"><span data-stu-id="f4ccd-116">Second parameter</span></span>

<span data-ttu-id="f4ccd-117">`BlockEncodingReflection`Unitario $U $ dell'hamiltoniana $U $.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="f4ccd-118">Poiché questo unitario soddisfa $U ^ 2 = I $, è anche una reflection.</span><span class="sxs-lookup"><span data-stu-id="f4ccd-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4ccd-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="f4ccd-119">Remarks</span></span>

<span data-ttu-id="f4ccd-120">Operazioni di esempio: preparare e annullare la preparazione dello stato $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ e costruire un Unity controllato da Multiply sono <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="f4ccd-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>
---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216541"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="91406-102">DecomposedIntoTimeStepsCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="91406-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="91406-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91406-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91406-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91406-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91406-105">Restituisce un'operazione che implementa l'integratore Trotter – Suzuki per una determinata operazione.</span><span class="sxs-lookup"><span data-stu-id="91406-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="91406-106">Input</span><span class="sxs-lookup"><span data-stu-id="91406-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="91406-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91406-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91406-108">Numero di operazioni da scomporre in passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="91406-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="91406-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="91406-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="91406-110">Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) per la scomposizione.</span><span class="sxs-lookup"><span data-stu-id="91406-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="91406-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91406-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91406-112">Seleziona l'ordine di utilizzo di Trotter-Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="91406-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="91406-113">Ordine 1 e anche Orders 2, 4, 6,... sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="91406-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="91406-114">Output: ([Double](xref:microsoft.quantum.lang-ref.double),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="91406-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="91406-115">Restituisce un Unity che implementa l'integratore Trotter – Suzuki, dove il primo parametro `Double` è la dimensione del passaggio di integrazione e il secondo parametro è la destinazione su cui si è agito.</span><span class="sxs-lookup"><span data-stu-id="91406-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91406-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="91406-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91406-117">T</span><span class="sxs-lookup"><span data-stu-id="91406-117">'T</span></span>

<span data-ttu-id="91406-118">Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="91406-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91406-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="91406-119">Remarks</span></span>

<span data-ttu-id="91406-120">Quando viene chiamato con `order` uguale a `1` , questa funzione restituisce un'operazione che può essere simulata da Trotter di ordine più basso-Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ dove è stata seguita la notazione di [quante-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) e si lascia che $ \lambda $ sia il tempo di evoluzione (rappresentato dal primo input dell'operazione restituita), e consentono a $ \{ H_j \} _ {j = 1} ^ {m} $ di essere il set di generatori dinamici (asimmetria-Hermitiane) integrati, in modo che `op(j, lambda, _)` venga simulato dall'operatore unitario $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="91406-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="91406-121">Analogamente, un oggetto `order` di `2` restituisce il secondo ordine simmetrico Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="91406-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="91406-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="91406-122">\end{align} $$</span></span>

<span data-ttu-id="91406-123">I valori pari più elevati di `order` vengono implementati usando la costruzione ricorsiva di [quanti-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="91406-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="91406-124">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="91406-124">References</span></span>

- [<span data-ttu-id="91406-125">*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="91406-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)
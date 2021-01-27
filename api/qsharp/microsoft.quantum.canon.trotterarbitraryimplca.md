---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operazione TrotterArbitraryImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840088"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="413cc-102">Operazione TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="413cc-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="413cc-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="413cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="413cc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="413cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="413cc-105">Implementazione ricorsiva dell'integratore uniforme di Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="413cc-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="413cc-106">Input</span><span class="sxs-lookup"><span data-stu-id="413cc-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="413cc-107">ordine: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="413cc-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="413cc-108">Ordine di Trotter-Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="413cc-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="413cc-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="413cc-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="413cc-110">Numero di operazioni da scomporre in passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="413cc-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="413cc-111">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="413cc-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="413cc-112">Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) e un registro Quantum (tipo `'T` ) per la scomposizione.</span><span class="sxs-lookup"><span data-stu-id="413cc-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="413cc-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="413cc-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="413cc-114">Moltiplicatore per le dimensioni di ogni passaggio della simulazione.</span><span class="sxs-lookup"><span data-stu-id="413cc-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="413cc-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="413cc-115">target : 'T</span></span>

<span data-ttu-id="413cc-116">Registro Quantum su cui si riportano le operazioni.</span><span class="sxs-lookup"><span data-stu-id="413cc-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="413cc-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="413cc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="413cc-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="413cc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="413cc-119">T</span><span class="sxs-lookup"><span data-stu-id="413cc-119">'T</span></span>

<span data-ttu-id="413cc-120">Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="413cc-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>
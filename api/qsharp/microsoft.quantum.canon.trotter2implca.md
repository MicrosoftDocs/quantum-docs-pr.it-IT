---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operazione Trotter2ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852028"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="6776f-102">Operazione Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="6776f-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="6776f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6776f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6776f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6776f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6776f-105">Implementazione del secondo ordine Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="6776f-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6776f-106">Input</span><span class="sxs-lookup"><span data-stu-id="6776f-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="6776f-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6776f-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6776f-108">Numero di operazioni da scomporre in passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="6776f-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="6776f-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6776f-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6776f-110">Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) e un registro Quantum (tipo `'T` ) per la scomposizione.</span><span class="sxs-lookup"><span data-stu-id="6776f-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="6776f-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6776f-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6776f-112">Moltiplicatore per le dimensioni di ogni passaggio della simulazione.</span><span class="sxs-lookup"><span data-stu-id="6776f-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="6776f-113">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="6776f-113">target : 'T</span></span>

<span data-ttu-id="6776f-114">Registro Quantum su cui si riportano le operazioni.</span><span class="sxs-lookup"><span data-stu-id="6776f-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6776f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6776f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6776f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6776f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6776f-117">T</span><span class="sxs-lookup"><span data-stu-id="6776f-117">'T</span></span>

<span data-ttu-id="6776f-118">Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="6776f-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="6776f-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="6776f-119">Example</span></span>

<span data-ttu-id="6776f-120">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="6776f-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="6776f-121">e</span><span class="sxs-lookup"><span data-stu-id="6776f-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```
---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operazione Trotter2ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715308"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="c529e-102">Operazione Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="c529e-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="c529e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c529e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c529e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c529e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c529e-105">Implementazione del secondo ordine Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="c529e-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c529e-106">Input</span><span class="sxs-lookup"><span data-stu-id="c529e-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="c529e-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c529e-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c529e-108">Numero di operazioni da scomporre in passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="c529e-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="c529e-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c529e-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c529e-110">Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) e un registro Quantum (tipo `'T` ) per la scomposizione.</span><span class="sxs-lookup"><span data-stu-id="c529e-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c529e-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c529e-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c529e-112">Moltiplicatore per le dimensioni di ogni passaggio della simulazione.</span><span class="sxs-lookup"><span data-stu-id="c529e-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c529e-113">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="c529e-113">target : 'T</span></span>

<span data-ttu-id="c529e-114">Registro Quantum su cui si riportano le operazioni.</span><span class="sxs-lookup"><span data-stu-id="c529e-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c529e-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c529e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c529e-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c529e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c529e-117">T</span><span class="sxs-lookup"><span data-stu-id="c529e-117">'T</span></span>

<span data-ttu-id="c529e-118">Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c529e-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>
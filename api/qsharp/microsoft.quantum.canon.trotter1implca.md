---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operazione Trotter1ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204794"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="3dca0-102">Operazione Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="3dca0-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="3dca0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3dca0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3dca0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dca0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dca0-105">Implementazione del primo ordine Trotter-Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="3dca0-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3dca0-106">Input</span><span class="sxs-lookup"><span data-stu-id="3dca0-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="3dca0-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3dca0-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3dca0-108">Numero di operazioni da scomporre in passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="3dca0-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="3dca0-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3dca0-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3dca0-110">Operazione che accetta un input di indice (tipo `Int` ) e un input temporale (tipo `Double` ) e un registro Quantum (tipo `'T` ) per la scomposizione.</span><span class="sxs-lookup"><span data-stu-id="3dca0-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3dca0-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3dca0-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3dca0-112">Moltiplicatore per le dimensioni di ogni passaggio della simulazione.</span><span class="sxs-lookup"><span data-stu-id="3dca0-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="3dca0-113">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="3dca0-113">target : 'T</span></span>

<span data-ttu-id="3dca0-114">Registro Quantum su cui si riportano le operazioni.</span><span class="sxs-lookup"><span data-stu-id="3dca0-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3dca0-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3dca0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3dca0-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3dca0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3dca0-117">T</span><span class="sxs-lookup"><span data-stu-id="3dca0-117">'T</span></span>

<span data-ttu-id="3dca0-118">Tipo su cui ogni passaggio temporale deve agire; in genere, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="3dca0-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>
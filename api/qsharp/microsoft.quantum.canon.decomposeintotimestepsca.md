---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716330"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="71bd3-102">DecomposeIntoTimeStepsCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="71bd3-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="71bd3-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71bd3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71bd3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71bd3-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="71bd3-105">DecomposeIntoTimeStepsCA è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="71bd3-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="71bd3-106">Usare invece <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>.</span><span class="sxs-lookup"><span data-stu-id="71bd3-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="71bd3-107">Input</span><span class="sxs-lookup"><span data-stu-id="71bd3-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="71bd3-108">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71bd3-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="71bd3-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="71bd3-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="71bd3-110">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71bd3-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="71bd3-111">Output: ([Double](xref:microsoft.quantum.lang-ref.double),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="71bd3-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71bd3-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="71bd3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71bd3-113">T</span><span class="sxs-lookup"><span data-stu-id="71bd3-113">'T</span></span>


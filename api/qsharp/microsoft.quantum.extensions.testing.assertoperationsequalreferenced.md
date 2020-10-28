---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: Operazione AssertOperationsEqualReferenced
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 2d39f74c68e48d2f2b8003b76885c9444056f8d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711623"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="dd5c9-102">Operazione AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="dd5c9-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="dd5c9-103">Spazio dei nomi: [Microsoft. Quantum. Extensions. testing](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="dd5c9-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="dd5c9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd5c9-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="dd5c9-105">AssertOperationsEqualReferenced è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="dd5c9-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="dd5c9-106">Usare invece <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>.</span><span class="sxs-lookup"><span data-stu-id="dd5c9-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="dd5c9-107">Usare @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span><span class="sxs-lookup"><span data-stu-id="dd5c9-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="dd5c9-108">Si noti che l'ordine degli argomenti di questa operazione è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="dd5c9-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="dd5c9-109">Input</span><span class="sxs-lookup"><span data-stu-id="dd5c9-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="dd5c9-110">effettivo: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="dd5c9-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="dd5c9-111">previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="dd5c9-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="dd5c9-112">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd5c9-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="dd5c9-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd5c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


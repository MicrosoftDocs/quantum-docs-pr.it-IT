---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operazione MultiplexOperationsWithAuxRegister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: f6a90657324f8528aaa2e9e511a7f8cbcd2f540f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715795"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="f7bff-102">Operazione MultiplexOperationsWithAuxRegister</span><span class="sxs-lookup"><span data-stu-id="f7bff-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="f7bff-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7bff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7bff-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7bff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7bff-105">Passaggio di implementazione di MultiplexOperations.</span><span class="sxs-lookup"><span data-stu-id="f7bff-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="f7bff-106">Input</span><span class="sxs-lookup"><span data-stu-id="f7bff-106">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="f7bff-107">unitaries:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="f7bff-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="f7bff-108">auxillaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f7bff-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="f7bff-109">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7bff-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="f7bff-110">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="f7bff-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f7bff-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7bff-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7bff-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f7bff-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7bff-113">T</span><span class="sxs-lookup"><span data-stu-id="f7bff-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="f7bff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7bff-114">See Also</span></span>

- [<span data-ttu-id="f7bff-115">Microsoft. Quantum. Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="f7bff-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)
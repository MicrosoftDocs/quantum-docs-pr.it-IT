---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operazione MultiplexOperationsWithAuxRegister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 530e78ba0c5ce6e0627177527daf2ccc56f537eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205984"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="a0a96-102">Operazione MultiplexOperationsWithAuxRegister</span><span class="sxs-lookup"><span data-stu-id="a0a96-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="a0a96-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0a96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0a96-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0a96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0a96-105">Passaggio di implementazione di MultiplexOperations.</span><span class="sxs-lookup"><span data-stu-id="a0a96-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a0a96-106">Input</span><span class="sxs-lookup"><span data-stu-id="a0a96-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="a0a96-107">unitaries:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="a0a96-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="a0a96-108">auxillaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a0a96-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="a0a96-109">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a0a96-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="a0a96-110">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="a0a96-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a0a96-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0a96-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a0a96-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a0a96-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0a96-113">T</span><span class="sxs-lookup"><span data-stu-id="a0a96-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="a0a96-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0a96-114">See Also</span></span>

- [<span data-ttu-id="a0a96-115">Microsoft. Quantum. Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="a0a96-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)
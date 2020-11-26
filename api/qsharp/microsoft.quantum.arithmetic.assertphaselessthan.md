---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operazione AssertPhaseLessThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223749"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="7514f-102">Operazione AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="7514f-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="7514f-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7514f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7514f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7514f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7514f-105">Dichiara che il `number` codificato in PhaseLittleEndian è minore di `value` .</span><span class="sxs-lookup"><span data-stu-id="7514f-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7514f-106">Input</span><span class="sxs-lookup"><span data-stu-id="7514f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="7514f-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7514f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7514f-108">`number` deve essere minore di questo.</span><span class="sxs-lookup"><span data-stu-id="7514f-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="7514f-109">numero: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7514f-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="7514f-110">Intero senza segno che viene confrontato con `value` .</span><span class="sxs-lookup"><span data-stu-id="7514f-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7514f-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7514f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7514f-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="7514f-112">Remarks</span></span>

<span data-ttu-id="7514f-113">La versione controllata di questa operazione ignora i controlli.</span><span class="sxs-lookup"><span data-stu-id="7514f-113">The controlled version of this operation ignores controls.</span></span>
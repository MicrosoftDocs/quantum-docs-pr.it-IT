---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operazione AssertPhaseLessThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843441"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="24787-102">Operazione AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="24787-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="24787-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="24787-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="24787-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24787-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24787-105">Dichiara che il `number` codificato in PhaseLittleEndian è minore di `value` .</span><span class="sxs-lookup"><span data-stu-id="24787-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="24787-106">Input</span><span class="sxs-lookup"><span data-stu-id="24787-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="24787-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="24787-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="24787-108">`number` deve essere minore di questo.</span><span class="sxs-lookup"><span data-stu-id="24787-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="24787-109">numero: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="24787-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="24787-110">Intero senza segno che viene confrontato con `value` .</span><span class="sxs-lookup"><span data-stu-id="24787-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24787-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24787-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="24787-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="24787-112">Remarks</span></span>

<span data-ttu-id="24787-113">La versione controllata di questa operazione ignora i controlli.</span><span class="sxs-lookup"><span data-stu-id="24787-113">The controlled version of this operation ignores controls.</span></span>
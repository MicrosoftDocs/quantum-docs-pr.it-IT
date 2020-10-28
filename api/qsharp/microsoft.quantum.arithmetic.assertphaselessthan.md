---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operazione AssertPhaseLessThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721374"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="a61fc-102">Operazione AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="a61fc-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="a61fc-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a61fc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a61fc-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a61fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a61fc-105">Dichiara che il `number` codificato in PhaseLittleEndian è minore di `value` .</span><span class="sxs-lookup"><span data-stu-id="a61fc-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a61fc-106">Input</span><span class="sxs-lookup"><span data-stu-id="a61fc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a61fc-107">valore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a61fc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a61fc-108">`number` deve essere minore di questo.</span><span class="sxs-lookup"><span data-stu-id="a61fc-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="a61fc-109">numero: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a61fc-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="a61fc-110">Intero senza segno che viene confrontato con `value` .</span><span class="sxs-lookup"><span data-stu-id="a61fc-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a61fc-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a61fc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a61fc-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="a61fc-112">Remarks</span></span>

<span data-ttu-id="a61fc-113">La versione controllata di questa operazione ignora i controlli.</span><span class="sxs-lookup"><span data-stu-id="a61fc-113">The controlled version of this operation ignores controls.</span></span>
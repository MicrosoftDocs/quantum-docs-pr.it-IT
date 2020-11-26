---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operazione AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223783"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="bd383-102">Operazione AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="bd383-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="bd383-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd383-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd383-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd383-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd383-105">Asserisce che il qubit più significativo di un registro qubit che rappresenta un Unsigned Integer si trova in un determinato stato.</span><span class="sxs-lookup"><span data-stu-id="bd383-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bd383-106">Input</span><span class="sxs-lookup"><span data-stu-id="bd383-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="bd383-107">valore: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="bd383-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="bd383-108">Valore del bit più alto da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="bd383-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="bd383-109">numero: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd383-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd383-110">Intero senza segno di cui viene verificato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="bd383-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd383-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd383-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bd383-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="bd383-112">Remarks</span></span>

<span data-ttu-id="bd383-113">La versione controllata di questa operazione ignora i controlli.</span><span class="sxs-lookup"><span data-stu-id="bd383-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd383-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd383-114">See Also</span></span>

- [<span data-ttu-id="bd383-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="bd383-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)
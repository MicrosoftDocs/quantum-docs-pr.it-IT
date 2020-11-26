---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operazione CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223290"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="d2aff-102">Operazione CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="d2aff-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="d2aff-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d2aff-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d2aff-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2aff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2aff-105">Copia il bit più significativo di un registro qubit `from` che rappresenta un Unsigned Integer in qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="d2aff-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d2aff-106">Input</span><span class="sxs-lookup"><span data-stu-id="d2aff-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="d2aff-107">da: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d2aff-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d2aff-108">Unsigned Integer dal quale viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="d2aff-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="d2aff-109">il numero intero è codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="d2aff-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d2aff-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d2aff-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d2aff-111">Qubit in cui viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="d2aff-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="d2aff-112">La codifica di bit è in base al calcolo.</span><span class="sxs-lookup"><span data-stu-id="d2aff-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2aff-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2aff-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d2aff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2aff-114">See Also</span></span>

- [<span data-ttu-id="d2aff-115">Microsoft. Quantum. aritmetic. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="d2aff-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)
---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: Operazione ApplyReversedOpBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202856"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="ebdd0-102">Operazione ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="ebdd0-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="ebdd0-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ebdd0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ebdd0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebdd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebdd0-105">Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.</span><span class="sxs-lookup"><span data-stu-id="ebdd0-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ebdd0-106">Input</span><span class="sxs-lookup"><span data-stu-id="ebdd0-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="ebdd0-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="ebdd0-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ebdd0-108">Operazione che agisce su un registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="ebdd0-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="ebdd0-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ebdd0-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ebdd0-110">Un registro Little-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="ebdd0-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebdd0-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebdd0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ebdd0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebdd0-112">See Also</span></span>

- [<span data-ttu-id="ebdd0-113">Microsoft. Quantum. aritmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="ebdd0-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="ebdd0-114">Microsoft. Quantum. aritmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="ebdd0-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="ebdd0-115">Microsoft. Quantum. aritmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="ebdd0-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
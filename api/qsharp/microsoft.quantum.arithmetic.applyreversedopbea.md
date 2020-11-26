---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Operazione ApplyReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 17d05e0914eead28ff0e04b858b003659d37ab7f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202822"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="b775a-102">Operazione ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="b775a-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="b775a-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b775a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b775a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b775a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b775a-105">Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.</span><span class="sxs-lookup"><span data-stu-id="b775a-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b775a-106">Input</span><span class="sxs-lookup"><span data-stu-id="b775a-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="b775a-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="b775a-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b775a-108">Operazione che agisce su un registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="b775a-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="b775a-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b775a-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b775a-110">Un registro Little-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="b775a-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b775a-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b775a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b775a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b775a-112">See Also</span></span>

- [<span data-ttu-id="b775a-113">Microsoft. Quantum. aritmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="b775a-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="b775a-114">Microsoft. Quantum. aritmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="b775a-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="b775a-115">Microsoft. Quantum. aritmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="b775a-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
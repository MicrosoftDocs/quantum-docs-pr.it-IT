---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: Operazione ApplyReversedOpBEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 3a5fef3bb4549433540b2a7b5e94d3cd2d527639
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202771"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="2d349-102">Operazione ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="2d349-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="2d349-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2d349-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2d349-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d349-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d349-105">Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.</span><span class="sxs-lookup"><span data-stu-id="2d349-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2d349-106">Input</span><span class="sxs-lookup"><span data-stu-id="2d349-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="2d349-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="2d349-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2d349-108">Operazione che agisce su un registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="2d349-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="2d349-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2d349-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2d349-110">Un registro Little-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="2d349-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d349-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d349-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2d349-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d349-112">See Also</span></span>

- [<span data-ttu-id="2d349-113">Microsoft. Quantum. aritmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="2d349-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="2d349-114">Microsoft. Quantum. aritmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="2d349-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="2d349-115">Microsoft. Quantum. aritmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="2d349-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Operazione ApplyReversedOpBECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 5c761fb8e1042a25cd2e88f1b33e597c7d9287f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202720"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="dba34-102">Operazione ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="dba34-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="dba34-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dba34-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dba34-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dba34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dba34-105">Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.</span><span class="sxs-lookup"><span data-stu-id="dba34-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dba34-106">Input</span><span class="sxs-lookup"><span data-stu-id="dba34-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="dba34-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dba34-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dba34-108">Operazione che agisce su un registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="dba34-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="dba34-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dba34-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dba34-110">Un registro Little-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="dba34-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dba34-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dba34-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="dba34-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dba34-112">See Also</span></span>

- [<span data-ttu-id="dba34-113">Microsoft. Quantum. aritmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="dba34-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="dba34-114">Microsoft. Quantum. aritmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="dba34-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="dba34-115">Microsoft. Quantum. aritmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="dba34-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
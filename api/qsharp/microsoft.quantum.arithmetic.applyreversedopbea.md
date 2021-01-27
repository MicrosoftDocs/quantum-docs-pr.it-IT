---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Operazione ApplyReversedOpBEA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1759764947cdbd84a1db945296d441a13f13767e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843594"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="bd096-102">Operazione ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="bd096-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="bd096-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd096-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd096-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd096-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd096-105">Applica un'operazione che accetta input big-endian a un registro che codifica un Unsigned Integer usando il formato little endian.</span><span class="sxs-lookup"><span data-stu-id="bd096-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bd096-106">Input</span><span class="sxs-lookup"><span data-stu-id="bd096-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="bd096-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="bd096-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bd096-108">Operazione che agisce su un registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="bd096-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="bd096-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd096-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd096-110">Un registro Little-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="bd096-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd096-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd096-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bd096-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd096-112">See Also</span></span>

- [<span data-ttu-id="bd096-113">Microsoft. Quantum. aritmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="bd096-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="bd096-114">Microsoft. Quantum. aritmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="bd096-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="bd096-115">Microsoft. Quantum. aritmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="bd096-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
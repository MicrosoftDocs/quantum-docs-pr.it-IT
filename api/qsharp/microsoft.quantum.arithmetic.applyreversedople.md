---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: Operazione ApplyReversedOpLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 16ce6842cdef8e519a13a45640edc3d79cdbce25
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202754"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="02e70-102">Operazione ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="02e70-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="02e70-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="02e70-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="02e70-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02e70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02e70-105">Applica un'operazione che accetta input little-endian a un registro che codifica un Unsigned Integer usando il formato big-endian.</span><span class="sxs-lookup"><span data-stu-id="02e70-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="02e70-106">Input</span><span class="sxs-lookup"><span data-stu-id="02e70-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="02e70-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="02e70-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="02e70-108">Operazione che agisce su un registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="02e70-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="02e70-109">registra: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="02e70-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="02e70-110">Registro Big-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="02e70-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02e70-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02e70-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="02e70-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02e70-112">See Also</span></span>

- [<span data-ttu-id="02e70-113">Microsoft. Quantum. aritmetic. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="02e70-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="02e70-114">Microsoft. Quantum. aritmetic. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="02e70-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="02e70-115">Microsoft. Quantum. aritmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="02e70-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
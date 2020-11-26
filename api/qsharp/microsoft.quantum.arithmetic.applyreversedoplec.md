---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Operazione ApplyReversedOpLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 75b6c0f09c0699b50d9ac1b0274e8074520fc241
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202652"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="887ba-102">Operazione ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="887ba-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="887ba-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="887ba-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="887ba-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="887ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="887ba-105">Applica un'operazione che accetta input little-endian a un registro che codifica un Unsigned Integer usando il formato big-endian.</span><span class="sxs-lookup"><span data-stu-id="887ba-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="887ba-106">Input</span><span class="sxs-lookup"><span data-stu-id="887ba-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="887ba-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="887ba-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="887ba-108">Operazione che agisce su un registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="887ba-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="887ba-109">registra: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="887ba-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="887ba-110">Registro Big-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="887ba-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="887ba-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="887ba-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="887ba-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="887ba-112">See Also</span></span>

- [<span data-ttu-id="887ba-113">Microsoft. Quantum. aritmetic. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="887ba-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="887ba-114">Microsoft. Quantum. aritmetic. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="887ba-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="887ba-115">Microsoft. Quantum. aritmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="887ba-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
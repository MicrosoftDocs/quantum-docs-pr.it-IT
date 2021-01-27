---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: Operazione ApplyReversedOpLEA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 572841410f16085256fdee9302038cd347476dd9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843519"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="0c872-102">Operazione ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="0c872-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="0c872-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0c872-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0c872-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c872-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c872-105">Applica un'operazione che accetta input little-endian a un registro che codifica un Unsigned Integer usando il formato big-endian.</span><span class="sxs-lookup"><span data-stu-id="0c872-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0c872-106">Input</span><span class="sxs-lookup"><span data-stu-id="0c872-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="0c872-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="0c872-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0c872-108">Operazione che agisce su un registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="0c872-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="0c872-109">registra: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0c872-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0c872-110">Registro Big-Endian da trasformare.</span><span class="sxs-lookup"><span data-stu-id="0c872-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c872-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c872-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0c872-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c872-112">See Also</span></span>

- [<span data-ttu-id="0c872-113">Microsoft. Quantum. aritmetic. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="0c872-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="0c872-114">Microsoft. Quantum. aritmetic. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="0c872-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="0c872-115">Microsoft. Quantum. aritmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="0c872-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
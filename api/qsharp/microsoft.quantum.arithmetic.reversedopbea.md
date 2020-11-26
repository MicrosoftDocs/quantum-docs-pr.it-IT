---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 69fd4401e6862a3a6afaa51fb5b8a3592768bb42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222304"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="9d6aa-102">ReversedOpBEA (funzione)</span><span class="sxs-lookup"><span data-stu-id="9d6aa-102">ReversedOpBEA function</span></span>

<span data-ttu-id="9d6aa-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9d6aa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9d6aa-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d6aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d6aa-105">Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.</span><span class="sxs-lookup"><span data-stu-id="9d6aa-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="9d6aa-106">Input</span><span class="sxs-lookup"><span data-stu-id="9d6aa-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="9d6aa-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="9d6aa-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9d6aa-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="9d6aa-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="9d6aa-109">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="9d6aa-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9d6aa-110">Nuova operazione che accetta l'input come registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="9d6aa-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d6aa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d6aa-111">See Also</span></span>

- [<span data-ttu-id="9d6aa-112">Microsoft. Quantum. aritmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="9d6aa-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="9d6aa-113">Microsoft. Quantum. aritmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="9d6aa-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="9d6aa-114">Microsoft. Quantum. aritmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="9d6aa-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="9d6aa-115">Microsoft. Quantum. aritmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="9d6aa-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
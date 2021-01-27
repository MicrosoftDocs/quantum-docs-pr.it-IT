---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 09bb99645d5946af0e0c654500165077691f8da3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846419"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="471dd-102">ReversedOpBECA (funzione)</span><span class="sxs-lookup"><span data-stu-id="471dd-102">ReversedOpBECA function</span></span>

<span data-ttu-id="471dd-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="471dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="471dd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="471dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="471dd-105">Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.</span><span class="sxs-lookup"><span data-stu-id="471dd-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="471dd-106">Input</span><span class="sxs-lookup"><span data-stu-id="471dd-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="471dd-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="471dd-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="471dd-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="471dd-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="471dd-109">Output: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="471dd-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="471dd-110">Nuova operazione che accetta l'input come registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="471dd-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="471dd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="471dd-111">See Also</span></span>

- [<span data-ttu-id="471dd-112">Microsoft. Quantum. aritmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="471dd-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="471dd-113">Microsoft. Quantum. aritmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="471dd-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="471dd-114">Microsoft. Quantum. aritmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="471dd-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="471dd-115">Microsoft. Quantum. aritmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="471dd-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
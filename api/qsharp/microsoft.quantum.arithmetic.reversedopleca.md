---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845743"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="a9ee6-102">ReversedOpLECA (funzione)</span><span class="sxs-lookup"><span data-stu-id="a9ee6-102">ReversedOpLECA function</span></span>

<span data-ttu-id="a9ee6-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a9ee6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a9ee6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9ee6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9ee6-105">Data un'operazione che accetta un input little-endian, restituisce una nuova operazione che accetta un input big-endian.</span><span class="sxs-lookup"><span data-stu-id="a9ee6-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a9ee6-106">Input</span><span class="sxs-lookup"><span data-stu-id="a9ee6-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="a9ee6-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a9ee6-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a9ee6-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="a9ee6-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="a9ee6-109">Output: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a9ee6-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a9ee6-110">Nuova operazione che accetta l'input come registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="a9ee6-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9ee6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9ee6-111">See Also</span></span>

- [<span data-ttu-id="a9ee6-112">Microsoft. Quantum. aritmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="a9ee6-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="a9ee6-113">Microsoft. Quantum. aritmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="a9ee6-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="a9ee6-114">Microsoft. Quantum. aritmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="a9ee6-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="a9ee6-115">Microsoft. Quantum. aritmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="a9ee6-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
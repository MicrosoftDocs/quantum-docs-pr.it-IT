---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 0674567f5d45890aa2f631b2e0e4d75d20a72449
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846443"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="a65e8-102">ReversedOpBEC (funzione)</span><span class="sxs-lookup"><span data-stu-id="a65e8-102">ReversedOpBEC function</span></span>

<span data-ttu-id="a65e8-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a65e8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a65e8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a65e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a65e8-105">Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.</span><span class="sxs-lookup"><span data-stu-id="a65e8-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a65e8-106">Input</span><span class="sxs-lookup"><span data-stu-id="a65e8-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="a65e8-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="a65e8-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a65e8-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="a65e8-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-ctl"></a><span data-ttu-id="a65e8-109">Output: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="a65e8-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a65e8-110">Nuova operazione che accetta l'input come registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="a65e8-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a65e8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a65e8-111">See Also</span></span>

- [<span data-ttu-id="a65e8-112">Microsoft. Quantum. aritmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="a65e8-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="a65e8-113">Microsoft. Quantum. aritmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="a65e8-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="a65e8-114">Microsoft. Quantum. aritmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="a65e8-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="a65e8-115">Microsoft. Quantum. aritmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="a65e8-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
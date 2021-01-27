---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 2dc6a596970f909af9c329dbe7002c165854cfec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846372"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="e43de-102">ReversedOpLEC (funzione)</span><span class="sxs-lookup"><span data-stu-id="e43de-102">ReversedOpLEC function</span></span>

<span data-ttu-id="e43de-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e43de-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e43de-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e43de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e43de-105">Data un'operazione che accetta un input little-endian, restituisce una nuova operazione che accetta un input big-endian.</span><span class="sxs-lookup"><span data-stu-id="e43de-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e43de-106">Input</span><span class="sxs-lookup"><span data-stu-id="e43de-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="e43de-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="e43de-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e43de-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="e43de-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="e43de-109">Output: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="e43de-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e43de-110">Nuova operazione che accetta l'input come registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="e43de-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="e43de-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e43de-111">See Also</span></span>

- [<span data-ttu-id="e43de-112">Microsoft. Quantum. aritmetic. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="e43de-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="e43de-113">Microsoft. Quantum. aritmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="e43de-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="e43de-114">Microsoft. Quantum. aritmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="e43de-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="e43de-115">Microsoft. Quantum. aritmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="e43de-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)
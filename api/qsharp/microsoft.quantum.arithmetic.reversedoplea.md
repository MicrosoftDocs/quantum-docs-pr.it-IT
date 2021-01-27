---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b0fcf1c735bb19308a381307e64314d9d961e5da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846436"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="b6d03-102">ReversedOpLEA (funzione)</span><span class="sxs-lookup"><span data-stu-id="b6d03-102">ReversedOpLEA function</span></span>

<span data-ttu-id="b6d03-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6d03-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6d03-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6d03-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6d03-105">Data un'operazione che accetta un input little-endian, restituisce una nuova operazione che accetta un input big-endian.</span><span class="sxs-lookup"><span data-stu-id="b6d03-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="b6d03-106">Input</span><span class="sxs-lookup"><span data-stu-id="b6d03-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="b6d03-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="b6d03-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b6d03-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="b6d03-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="b6d03-109">Output: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="b6d03-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b6d03-110">Nuova operazione che accetta l'input come registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="b6d03-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6d03-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6d03-111">See Also</span></span>

- [<span data-ttu-id="b6d03-112">Microsoft. Quantum. aritmetic. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="b6d03-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="b6d03-113">Microsoft. Quantum. aritmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="b6d03-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="b6d03-114">Microsoft. Quantum. aritmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="b6d03-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="b6d03-115">Microsoft. Quantum. aritmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="b6d03-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)
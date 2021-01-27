---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846478"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="251df-102">ReversedOpBE (funzione)</span><span class="sxs-lookup"><span data-stu-id="251df-102">ReversedOpBE function</span></span>

<span data-ttu-id="251df-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="251df-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="251df-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="251df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="251df-105">Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.</span><span class="sxs-lookup"><span data-stu-id="251df-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="251df-106">Input</span><span class="sxs-lookup"><span data-stu-id="251df-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="251df-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="251df-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="251df-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="251df-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="251df-109">Output: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="251df-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="251df-110">Nuova operazione che accetta l'input come registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="251df-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="251df-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="251df-111">See Also</span></span>

- [<span data-ttu-id="251df-112">Microsoft. Quantum. aritmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="251df-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="251df-113">Microsoft. Quantum. aritmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="251df-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="251df-114">Microsoft. Quantum. aritmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="251df-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="251df-115">Microsoft. Quantum. aritmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="251df-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
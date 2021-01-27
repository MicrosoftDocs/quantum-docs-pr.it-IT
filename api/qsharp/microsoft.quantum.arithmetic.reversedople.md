---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846390"
---
# <a name="reversedople-function"></a><span data-ttu-id="4d71f-102">ReversedOpLE (funzione)</span><span class="sxs-lookup"><span data-stu-id="4d71f-102">ReversedOpLE function</span></span>

<span data-ttu-id="4d71f-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4d71f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4d71f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d71f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d71f-105">Data un'operazione che accetta un input little-endian, restituisce una nuova operazione che accetta un input big-endian.</span><span class="sxs-lookup"><span data-stu-id="4d71f-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="4d71f-106">Input</span><span class="sxs-lookup"><span data-stu-id="4d71f-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="4d71f-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="4d71f-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4d71f-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="4d71f-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="4d71f-109">Output: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="4d71f-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4d71f-110">Nuova operazione che accetta l'input come registro big-endian.</span><span class="sxs-lookup"><span data-stu-id="4d71f-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d71f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d71f-111">See Also</span></span>

- [<span data-ttu-id="4d71f-112">Microsoft. Quantum. aritmetic. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="4d71f-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="4d71f-113">Microsoft. Quantum. aritmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="4d71f-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="4d71f-114">Microsoft. Quantum. aritmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="4d71f-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="4d71f-115">Microsoft. Quantum. aritmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="4d71f-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)
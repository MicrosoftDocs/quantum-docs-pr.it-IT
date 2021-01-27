---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 392b97171bcfb9d35a38189fc9c27e61cf9cf7d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846467"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="eec3e-102">ReversedOpBEA (funzione)</span><span class="sxs-lookup"><span data-stu-id="eec3e-102">ReversedOpBEA function</span></span>

<span data-ttu-id="eec3e-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="eec3e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="eec3e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eec3e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eec3e-105">Data un'operazione che accetta un input big endian, restituisce una nuova operazione che accetta un input little-endian.</span><span class="sxs-lookup"><span data-stu-id="eec3e-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="eec3e-106">Input</span><span class="sxs-lookup"><span data-stu-id="eec3e-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="eec3e-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) bigEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="eec3e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eec3e-108">Operazione il cui input deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="eec3e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="eec3e-109">Output: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="eec3e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eec3e-110">Nuova operazione che accetta l'input come registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="eec3e-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="eec3e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eec3e-111">See Also</span></span>

- [<span data-ttu-id="eec3e-112">Microsoft. Quantum. aritmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="eec3e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="eec3e-113">Microsoft. Quantum. aritmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="eec3e-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="eec3e-114">Microsoft. Quantum. aritmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="eec3e-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="eec3e-115">Microsoft. Quantum. aritmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="eec3e-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
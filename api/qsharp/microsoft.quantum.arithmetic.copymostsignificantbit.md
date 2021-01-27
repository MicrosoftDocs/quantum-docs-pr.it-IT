---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operazione CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843275"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="b0bd5-102">Operazione CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="b0bd5-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="b0bd5-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b0bd5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b0bd5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0bd5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0bd5-105">Copia il bit più significativo di un registro qubit `from` che rappresenta un Unsigned Integer in qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="b0bd5-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b0bd5-106">Input</span><span class="sxs-lookup"><span data-stu-id="b0bd5-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="b0bd5-107">da: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0bd5-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0bd5-108">Unsigned Integer dal quale viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="b0bd5-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="b0bd5-109">il numero intero è codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="b0bd5-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b0bd5-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b0bd5-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b0bd5-111">Qubit in cui viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="b0bd5-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="b0bd5-112">La codifica di bit è in base al calcolo.</span><span class="sxs-lookup"><span data-stu-id="b0bd5-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0bd5-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0bd5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b0bd5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0bd5-114">See Also</span></span>

- [<span data-ttu-id="b0bd5-115">Microsoft. Quantum. aritmetic. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="b0bd5-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)
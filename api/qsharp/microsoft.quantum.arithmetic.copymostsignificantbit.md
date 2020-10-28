---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operazione CopyMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721215"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="e3c90-102">Operazione CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="e3c90-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="e3c90-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e3c90-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e3c90-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3c90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3c90-105">Copia il bit più significativo di un registro qubit `from` che rappresenta un Unsigned Integer in qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="e3c90-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e3c90-106">Input</span><span class="sxs-lookup"><span data-stu-id="e3c90-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="e3c90-107">da: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e3c90-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e3c90-108">Unsigned Integer dal quale viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="e3c90-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="e3c90-109">il numero intero è codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="e3c90-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e3c90-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e3c90-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e3c90-111">Qubit in cui viene copiato il bit più alto.</span><span class="sxs-lookup"><span data-stu-id="e3c90-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="e3c90-112">La codifica di bit è in base al calcolo.</span><span class="sxs-lookup"><span data-stu-id="e3c90-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3c90-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3c90-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e3c90-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3c90-114">See Also</span></span>

- [<span data-ttu-id="e3c90-115">Microsoft. Quantum. aritmetic. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="e3c90-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)
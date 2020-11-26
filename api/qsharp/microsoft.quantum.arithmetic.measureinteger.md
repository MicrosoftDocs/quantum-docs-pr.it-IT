---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operazione MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222644"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="8643c-102">Operazione MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="8643c-102">MeasureInteger operation</span></span>

<span data-ttu-id="8643c-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8643c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8643c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8643c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8643c-105">Misura il contenuto di un registro Quantum e lo converte in un numero intero.</span><span class="sxs-lookup"><span data-stu-id="8643c-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="8643c-106">La misurazione viene eseguita rispetto alla base di calcolo standard, ovvero eigenbasis di `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="8643c-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="8643c-107">Input</span><span class="sxs-lookup"><span data-stu-id="8643c-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="8643c-108">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8643c-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8643c-109">Registro Quantum nella codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="8643c-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="8643c-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8643c-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8643c-111">Unsigned Integer che contiene il valore misurato di `target` .</span><span class="sxs-lookup"><span data-stu-id="8643c-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8643c-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="8643c-112">Remarks</span></span>

<span data-ttu-id="8643c-113">Questa operazione Reimposta il registro di input sullo stato $ \ket{00\cdots 0} $, adatto per il rilascio di nuovo in un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8643c-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="8643c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8643c-114">See Also</span></span>

- [<span data-ttu-id="8643c-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="8643c-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)
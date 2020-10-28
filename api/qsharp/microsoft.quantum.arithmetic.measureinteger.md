---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operazione MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720966"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="89023-102">Operazione MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="89023-102">MeasureInteger operation</span></span>

<span data-ttu-id="89023-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="89023-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="89023-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89023-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89023-105">Misura il contenuto di un registro Quantum e lo converte in un numero intero.</span><span class="sxs-lookup"><span data-stu-id="89023-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="89023-106">La misurazione viene eseguita rispetto alla base di calcolo standard, ovvero eigenbasis di `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="89023-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="89023-107">Input</span><span class="sxs-lookup"><span data-stu-id="89023-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="89023-108">destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="89023-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="89023-109">Registro Quantum nella codifica little-endian.</span><span class="sxs-lookup"><span data-stu-id="89023-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="89023-110">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89023-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89023-111">Unsigned Integer che contiene il valore misurato di `target` .</span><span class="sxs-lookup"><span data-stu-id="89023-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="89023-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="89023-112">Remarks</span></span>

<span data-ttu-id="89023-113">Questa operazione Reimposta il registro di input sullo stato $ \ket{00\cdots 0} $, adatto per il rilascio di nuovo in un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="89023-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="89023-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89023-114">See Also</span></span>

- [<span data-ttu-id="89023-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="89023-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)
---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operazione QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205576"
---
# <a name="qftle-operation"></a><span data-ttu-id="b7e00-102">Operazione QFTLE</span><span class="sxs-lookup"><span data-stu-id="b7e00-102">QFTLE operation</span></span>

<span data-ttu-id="b7e00-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7e00-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7e00-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7e00-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7e00-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione little-endian.</span><span class="sxs-lookup"><span data-stu-id="b7e00-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b7e00-106">Input</span><span class="sxs-lookup"><span data-stu-id="b7e00-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="b7e00-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b7e00-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b7e00-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="b7e00-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7e00-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7e00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b7e00-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="b7e00-110">Remarks</span></span>

<span data-ttu-id="b7e00-111">Si presuppone che l'input e l'output si trovino nella codifica little endian.</span><span class="sxs-lookup"><span data-stu-id="b7e00-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7e00-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7e00-112">See Also</span></span>

- [<span data-ttu-id="b7e00-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="b7e00-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operazione ApplyQuantumFourierTransformBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209044"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="62e67-102">Operazione ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="62e67-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="62e67-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="62e67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="62e67-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62e67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62e67-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione big-endian.</span><span class="sxs-lookup"><span data-stu-id="62e67-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="62e67-106">Input</span><span class="sxs-lookup"><span data-stu-id="62e67-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="62e67-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="62e67-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="62e67-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="62e67-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="62e67-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62e67-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62e67-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="62e67-110">Remarks</span></span>

<span data-ttu-id="62e67-111">Si presuppone che l'input e l'output si trovino nella codifica big endian.</span><span class="sxs-lookup"><span data-stu-id="62e67-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="62e67-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62e67-112">See Also</span></span>

- [<span data-ttu-id="62e67-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="62e67-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="62e67-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="62e67-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)
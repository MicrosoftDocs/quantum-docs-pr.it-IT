---
uid: Microsoft.Quantum.Canon.QFT
title: Operazione QFT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205533"
---
# <a name="qft-operation"></a><span data-ttu-id="3c152-102">Operazione QFT</span><span class="sxs-lookup"><span data-stu-id="3c152-102">QFT operation</span></span>

<span data-ttu-id="3c152-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c152-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c152-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c152-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c152-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione big-endian.</span><span class="sxs-lookup"><span data-stu-id="3c152-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3c152-106">Input</span><span class="sxs-lookup"><span data-stu-id="3c152-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="3c152-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3c152-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3c152-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="3c152-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c152-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c152-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c152-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="3c152-110">Remarks</span></span>

<span data-ttu-id="3c152-111">Si presuppone che l'input e l'output si trovino nella codifica big endian.</span><span class="sxs-lookup"><span data-stu-id="3c152-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c152-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c152-112">See Also</span></span>

- [<span data-ttu-id="3c152-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="3c152-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
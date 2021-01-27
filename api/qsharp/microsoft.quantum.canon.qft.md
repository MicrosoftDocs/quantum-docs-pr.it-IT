---
uid: Microsoft.Quantum.Canon.QFT
title: Operazione QFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852287"
---
# <a name="qft-operation"></a><span data-ttu-id="0931b-102">Operazione QFT</span><span class="sxs-lookup"><span data-stu-id="0931b-102">QFT operation</span></span>

<span data-ttu-id="0931b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0931b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0931b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0931b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0931b-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione big-endian.</span><span class="sxs-lookup"><span data-stu-id="0931b-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0931b-106">Input</span><span class="sxs-lookup"><span data-stu-id="0931b-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="0931b-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0931b-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0931b-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="0931b-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0931b-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0931b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0931b-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="0931b-110">Remarks</span></span>

<span data-ttu-id="0931b-111">Si presuppone che l'input e l'output si trovino nella codifica big endian.</span><span class="sxs-lookup"><span data-stu-id="0931b-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="0931b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0931b-112">See Also</span></span>

- [<span data-ttu-id="0931b-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="0931b-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
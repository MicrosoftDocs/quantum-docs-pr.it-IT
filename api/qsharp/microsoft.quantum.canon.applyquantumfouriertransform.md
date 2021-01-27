---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operazione ApplyQuantumFourierTransform
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844771"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="9f055-102">Operazione ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="9f055-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="9f055-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f055-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f055-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f055-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f055-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione little-endian.</span><span class="sxs-lookup"><span data-stu-id="9f055-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9f055-106">Input</span><span class="sxs-lookup"><span data-stu-id="9f055-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="9f055-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9f055-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9f055-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="9f055-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f055-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f055-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9f055-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="9f055-110">Remarks</span></span>

<span data-ttu-id="9f055-111">Si presuppone che l'input e l'output si trovino nella codifica little endian.</span><span class="sxs-lookup"><span data-stu-id="9f055-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f055-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f055-112">See Also</span></span>

- [<span data-ttu-id="9f055-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="9f055-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
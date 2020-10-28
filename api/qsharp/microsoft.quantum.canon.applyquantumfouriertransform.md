---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operazione ApplyQuantumFourierTransform
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717797"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="bea8a-102">Operazione ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="bea8a-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="bea8a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bea8a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bea8a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bea8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bea8a-105">Esegue la trasformazione Quantum Fourier in un registro Quantum contenente un Integer nella rappresentazione little-endian.</span><span class="sxs-lookup"><span data-stu-id="bea8a-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bea8a-106">Input</span><span class="sxs-lookup"><span data-stu-id="bea8a-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="bea8a-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bea8a-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bea8a-108">Registro Quantum a cui viene applicata la trasformazione Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="bea8a-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="bea8a-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bea8a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bea8a-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="bea8a-110">Remarks</span></span>

<span data-ttu-id="bea8a-111">Si presuppone che l'input e l'output si trovino nella codifica little endian.</span><span class="sxs-lookup"><span data-stu-id="bea8a-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="bea8a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bea8a-112">See Also</span></span>

- [<span data-ttu-id="bea8a-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="bea8a-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
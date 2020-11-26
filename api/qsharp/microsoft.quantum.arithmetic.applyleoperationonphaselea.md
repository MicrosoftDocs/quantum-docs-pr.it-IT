---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: Operazione ApplyLEOperationOnPhaseLEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 408bd4e5d7146a74d7aec233765a63b2086b8ede
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190854"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="019c5-102">Operazione ApplyLEOperationOnPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="019c5-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="019c5-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="019c5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="019c5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="019c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="019c5-105">Applica un'operazione che accetta un <xref:microsoft.quantum.arithmetic.phaselittleendian> registro come input per un registro di destinazione di tipo <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="019c5-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="019c5-106">Input</span><span class="sxs-lookup"><span data-stu-id="019c5-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="019c5-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ</span><span class="sxs-lookup"><span data-stu-id="019c5-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="019c5-108">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="019c5-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="019c5-109">destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="019c5-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="019c5-110">Registro a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="019c5-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="019c5-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="019c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="019c5-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="019c5-112">Remarks</span></span>

<span data-ttu-id="019c5-113">Il registro viene trasformato in `LittleEndian` mediante l'utilizzo di <xref:microsoft.quantum.canon.qftle> e viene quindi restituito alla relativa rappresentazione originale dopo l'applicazione di `op` .</span><span class="sxs-lookup"><span data-stu-id="019c5-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="019c5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="019c5-114">See Also</span></span>

- [<span data-ttu-id="019c5-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="019c5-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="019c5-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="019c5-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="019c5-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="019c5-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)
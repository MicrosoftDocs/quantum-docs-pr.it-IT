---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: Operazione ApplyLEOperationOnPhaseLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: dafe27f66f967fb641a8898672e124c0a51fe687
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190837"
---
# <a name="applyleoperationonphaselec-operation"></a><span data-ttu-id="a49f5-102">Operazione ApplyLEOperationOnPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="a49f5-102">ApplyLEOperationOnPhaseLEC operation</span></span>

<span data-ttu-id="a49f5-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a49f5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a49f5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a49f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a49f5-105">Applica un'operazione che accetta un <xref:microsoft.quantum.arithmetic.phaselittleendian> registro come input per un registro di destinazione di tipo <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="a49f5-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="a49f5-106">Input</span><span class="sxs-lookup"><span data-stu-id="a49f5-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="a49f5-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è CTL</span><span class="sxs-lookup"><span data-stu-id="a49f5-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a49f5-108">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a49f5-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="a49f5-109">destinazione: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a49f5-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="a49f5-110">Registro a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a49f5-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a49f5-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a49f5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a49f5-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a49f5-112">Remarks</span></span>

<span data-ttu-id="a49f5-113">Il registro viene trasformato in `LittleEndian` mediante l'utilizzo di <xref:microsoft.quantum.canon.qftle> e viene quindi restituito alla relativa rappresentazione originale dopo l'applicazione di `op` .</span><span class="sxs-lookup"><span data-stu-id="a49f5-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a49f5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a49f5-114">See Also</span></span>

- [<span data-ttu-id="a49f5-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="a49f5-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="a49f5-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="a49f5-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="a49f5-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="a49f5-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)
---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operazione CarryOutCoreCDKM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223545"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="da6aa-102">Operazione CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="da6aa-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="da6aa-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="da6aa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="da6aa-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da6aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da6aa-105">Operazione di base in RippleCarryAdderCDKM, usata con l'operazione ApplyOuterCDKMAdder precedente, ad esempio coniugata con questa operazione per ottenere il funzionamento interno di RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="da6aa-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="da6aa-106">Questa operazione calcola il qubit di esecuzione e applica una sequenza di controlli NOT in parte dell'input `ys` .</span><span class="sxs-lookup"><span data-stu-id="da6aa-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da6aa-107">Input</span><span class="sxs-lookup"><span data-stu-id="da6aa-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="da6aa-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da6aa-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="da6aa-109">Primo registro qubit.</span><span class="sxs-lookup"><span data-stu-id="da6aa-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="da6aa-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da6aa-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="da6aa-111">Secondo registro qubit.</span><span class="sxs-lookup"><span data-stu-id="da6aa-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="da6aa-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da6aa-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da6aa-113">Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.</span><span class="sxs-lookup"><span data-stu-id="da6aa-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="da6aa-114">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da6aa-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da6aa-115">Eseguire qubit nell'operazione RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="da6aa-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da6aa-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da6aa-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="da6aa-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="da6aa-117">References</span></span>

- <span data-ttu-id="da6aa-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="da6aa-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1
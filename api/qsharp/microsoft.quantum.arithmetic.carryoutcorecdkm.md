---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operazione CarryOutCoreCDKM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843335"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="72c71-102">Operazione CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="72c71-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="72c71-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="72c71-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="72c71-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72c71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72c71-105">Operazione di base in RippleCarryAdderCDKM, usata con l'operazione ApplyOuterCDKMAdder precedente, ad esempio coniugata con questa operazione per ottenere il funzionamento interno di RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="72c71-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="72c71-106">Questa operazione calcola il qubit di esecuzione e applica una sequenza di controlli NOT in parte dell'input `ys` .</span><span class="sxs-lookup"><span data-stu-id="72c71-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72c71-107">Input</span><span class="sxs-lookup"><span data-stu-id="72c71-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="72c71-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="72c71-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="72c71-109">Primo registro qubit.</span><span class="sxs-lookup"><span data-stu-id="72c71-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="72c71-110">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="72c71-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="72c71-111">Secondo registro qubit.</span><span class="sxs-lookup"><span data-stu-id="72c71-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="72c71-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72c71-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72c71-113">Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.</span><span class="sxs-lookup"><span data-stu-id="72c71-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="72c71-114">porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72c71-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72c71-115">Eseguire qubit nell'operazione RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="72c71-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72c71-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72c71-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="72c71-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="72c71-117">References</span></span>

- <span data-ttu-id="72c71-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="72c71-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1
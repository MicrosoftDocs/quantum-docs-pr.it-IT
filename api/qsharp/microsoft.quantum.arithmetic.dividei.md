---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operazione divide
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846691"
---
# <a name="dividei-operation"></a><span data-ttu-id="cc561-102">Operazione divide</span><span class="sxs-lookup"><span data-stu-id="cc561-102">DivideI operation</span></span>

<span data-ttu-id="cc561-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cc561-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cc561-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cc561-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cc561-105">Divide due interi quantici.</span><span class="sxs-lookup"><span data-stu-id="cc561-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cc561-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc561-106">Description</span></span>

<span data-ttu-id="cc561-107">`xs` manterrà il resto `xs - floor(xs/ys) * ys` e conterrà `result` `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="cc561-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="cc561-108">Input</span><span class="sxs-lookup"><span data-stu-id="cc561-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="cc561-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cc561-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cc561-110">$n dividendi $ bit, verrà sostituito dal resto.</span><span class="sxs-lookup"><span data-stu-id="cc561-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="cc561-111">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cc561-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cc561-112">divisore $n $ bit</span><span class="sxs-lookup"><span data-stu-id="cc561-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="cc561-113">risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cc561-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cc561-114">$n risultato $-bit, deve trovarsi nello stato $ \ket {0} $ inizialmente e verrà sostituito dal risultato della divisione di interi.</span><span class="sxs-lookup"><span data-stu-id="cc561-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc561-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc561-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cc561-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="cc561-116">Remarks</span></span>

<span data-ttu-id="cc561-117">Usa un approccio standard di spostamento e sottrazione per implementare la divisione.</span><span class="sxs-lookup"><span data-stu-id="cc561-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="cc561-118">La versione controllata è specializzata, di conseguenza la sottrazione non richiede controlli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cc561-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>
---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operazione multiplyi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222508"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="c97d7-102">Operazione multiplyi</span><span class="sxs-lookup"><span data-stu-id="c97d7-102">MultiplyI operation</span></span>

<span data-ttu-id="c97d7-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c97d7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c97d7-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c97d7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c97d7-105">Moltiplica integer `xs` per intero `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.</span><span class="sxs-lookup"><span data-stu-id="c97d7-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c97d7-106">Input</span><span class="sxs-lookup"><span data-stu-id="c97d7-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c97d7-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c97d7-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c97d7-108">$n $ bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c97d7-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c97d7-109">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c97d7-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c97d7-110">moltiplicatore $n $ bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c97d7-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="c97d7-111">risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c97d7-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c97d7-112">il risultato $2n $-bit (LittleEndian) deve essere in stato inizialmente $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c97d7-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c97d7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c97d7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c97d7-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="c97d7-114">Remarks</span></span>

<span data-ttu-id="c97d7-115">Usa un approccio standard di spostamento e aggiunta per implementare la moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="c97d7-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="c97d7-116">La versione controllata è stata migliorata copiando $x _i $ in un ancilla qubit condizionato sul qubits di controllo e quindi controllando l'aggiunta in ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="c97d7-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>
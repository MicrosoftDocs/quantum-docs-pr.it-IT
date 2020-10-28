---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operazione multiplyi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719763"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="0f8be-102">Operazione multiplyi</span><span class="sxs-lookup"><span data-stu-id="0f8be-102">MultiplyI operation</span></span>

<span data-ttu-id="0f8be-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0f8be-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0f8be-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f8be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f8be-105">Moltiplica integer `xs` per intero `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.</span><span class="sxs-lookup"><span data-stu-id="0f8be-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="0f8be-106">Input</span><span class="sxs-lookup"><span data-stu-id="0f8be-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0f8be-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f8be-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f8be-108">$n $ bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f8be-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0f8be-109">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f8be-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f8be-110">moltiplicatore $n $ bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f8be-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="0f8be-111">risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f8be-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f8be-112">il risultato $2n $-bit (LittleEndian) deve essere in stato inizialmente $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0f8be-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f8be-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f8be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f8be-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="0f8be-114">Remarks</span></span>

<span data-ttu-id="0f8be-115">Usa un approccio standard di spostamento e aggiunta per implementare la moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="0f8be-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="0f8be-116">La versione controllata è stata migliorata copiando $x _i $ in un ancilla qubit condizionato sul qubits di controllo e quindi controllando l'aggiunta in ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="0f8be-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>
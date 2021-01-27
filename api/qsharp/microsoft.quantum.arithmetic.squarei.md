---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operazione squarei
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846305"
---
# <a name="squarei-operation"></a><span data-ttu-id="50733-102">Operazione squarei</span><span class="sxs-lookup"><span data-stu-id="50733-102">SquareI operation</span></span>

<span data-ttu-id="50733-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="50733-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="50733-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="50733-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="50733-105">Calcola il quadrato del valore integer `xs` in `result` , che deve essere inizialmente zero.</span><span class="sxs-lookup"><span data-stu-id="50733-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="50733-106">Input</span><span class="sxs-lookup"><span data-stu-id="50733-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="50733-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="50733-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="50733-108">$n il numero di $ bit al quadrato (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="50733-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="50733-109">risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="50733-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="50733-110">il risultato $2n $-bit (LittleEndian) deve essere in stato inizialmente $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="50733-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50733-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50733-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="50733-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="50733-112">Remarks</span></span>

<span data-ttu-id="50733-113">Usa un approccio standard di spostamento e aggiunta per calcolare il quadrato.</span><span class="sxs-lookup"><span data-stu-id="50733-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="50733-114">Salva $n-$1 qubits rispetto alla soluzione diretta che copia prima di tutto XS prima di applicare un moltiplicatore regolare e quindi di eseguire l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="50733-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>
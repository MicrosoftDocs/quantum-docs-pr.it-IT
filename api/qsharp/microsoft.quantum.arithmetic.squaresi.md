---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operazione Squares
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7fe4d27b974a06b019a2b15710fbc51b598027b4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221828"
---
# <a name="squaresi-operation"></a><span data-ttu-id="4f824-102">Operazione Squares</span><span class="sxs-lookup"><span data-stu-id="4f824-102">SquareSI operation</span></span>

<span data-ttu-id="4f824-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f824-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f824-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4f824-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4f824-105">Un intero con segno quadrato `xs` e archivia il risultato in `result` , che deve essere inizialmente zero.</span><span class="sxs-lookup"><span data-stu-id="4f824-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f824-106">Input</span><span class="sxs-lookup"><span data-stu-id="4f824-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="4f824-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f824-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4f824-108">da n bit intero a quadrato (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f824-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="4f824-109">risultato: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f824-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4f824-110">il risultato a 2n bit (SignedLittleEndian) deve essere in stato inizialmente $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4f824-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f824-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f824-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f824-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="4f824-112">Remarks</span></span>

<span data-ttu-id="4f824-113">L'implementazione si basa su IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="4f824-113">The implementation relies on IntegerSquare.</span></span>
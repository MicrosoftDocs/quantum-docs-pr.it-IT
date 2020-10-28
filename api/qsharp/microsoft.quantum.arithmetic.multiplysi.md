---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operazione MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719751"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="88e93-102">Operazione MultiplySI</span><span class="sxs-lookup"><span data-stu-id="88e93-102">MultiplySI operation</span></span>

<span data-ttu-id="88e93-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="88e93-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="88e93-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88e93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88e93-105">Moltiplica il valore intero `xs` con segno per intero con segno `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.</span><span class="sxs-lookup"><span data-stu-id="88e93-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="88e93-106">Input</span><span class="sxs-lookup"><span data-stu-id="88e93-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="88e93-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e93-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="88e93-108">multiplicand a n bit (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e93-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="88e93-109">Ys: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e93-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="88e93-110">moltiplicatore n bit (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e93-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="88e93-111">risultato: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e93-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="88e93-112">il risultato a 2n bit (SignedLittleEndian) deve essere in stato inizialmente $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="88e93-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88e93-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88e93-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


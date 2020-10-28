---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operazione CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721278"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="f6a44-102">Operazione CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="f6a44-102">CompareGTSI operation</span></span>

<span data-ttu-id="f6a44-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f6a44-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f6a44-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6a44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6a44-105">Wrapper per il confronto di interi con segno: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="f6a44-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f6a44-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6a44-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="f6a44-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f6a44-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="f6a44-108">Primo $n numero di $ bit</span><span class="sxs-lookup"><span data-stu-id="f6a44-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="f6a44-109">Ys: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f6a44-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="f6a44-110">Secondo numero $n $ bit</span><span class="sxs-lookup"><span data-stu-id="f6a44-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="f6a44-111">risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f6a44-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f6a44-112">Verrà capovolto se $xs > YS $</span><span class="sxs-lookup"><span data-stu-id="f6a44-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="f6a44-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6a44-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


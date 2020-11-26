---
uid: Microsoft.Quantum.Math.ModL
title: ModL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227795"
---
# <a name="modl-function"></a><span data-ttu-id="19f47-102">ModL (funzione)</span><span class="sxs-lookup"><span data-stu-id="19f47-102">ModL function</span></span>

<span data-ttu-id="19f47-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="19f47-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="19f47-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19f47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19f47-105">Restituisce il modulo di un numero rispetto a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="19f47-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="19f47-106">Input</span><span class="sxs-lookup"><span data-stu-id="19f47-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="19f47-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="19f47-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="19f47-108">Input $a $ di cui deve essere restituito il modulo.</span><span class="sxs-lookup"><span data-stu-id="19f47-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="19f47-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="19f47-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="19f47-110">Numero rispetto al quale deve essere restituito il modulo di $a $.</span><span class="sxs-lookup"><span data-stu-id="19f47-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="19f47-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="19f47-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="19f47-112">Modulo $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="19f47-112">The modulus $a \bmod b$.</span></span>
---
uid: Microsoft.Quantum.Math.ModL
title: ModL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846829"
---
# <a name="modl-function"></a><span data-ttu-id="6ab74-102">ModL (funzione)</span><span class="sxs-lookup"><span data-stu-id="6ab74-102">ModL function</span></span>

<span data-ttu-id="6ab74-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ab74-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ab74-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ab74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ab74-105">Restituisce il modulo di un numero rispetto a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="6ab74-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="6ab74-106">Input</span><span class="sxs-lookup"><span data-stu-id="6ab74-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6ab74-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ab74-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ab74-108">Input $a $ di cui deve essere restituito il modulo.</span><span class="sxs-lookup"><span data-stu-id="6ab74-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="6ab74-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ab74-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ab74-110">Numero rispetto al quale deve essere restituito il modulo di $a $.</span><span class="sxs-lookup"><span data-stu-id="6ab74-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="6ab74-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ab74-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ab74-112">Modulo $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="6ab74-112">The modulus $a \bmod b$.</span></span>
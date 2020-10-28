---
uid: Microsoft.Quantum.Logical.Xor
title: XOR (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723292"
---
# <a name="xor-function"></a><span data-ttu-id="95dd5-102">XOR (funzione)</span><span class="sxs-lookup"><span data-stu-id="95dd5-102">Xor function</span></span>

<span data-ttu-id="95dd5-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="95dd5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="95dd5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95dd5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95dd5-105">Restituisce la disgiunzione esclusiva booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="95dd5-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="95dd5-106">Input</span><span class="sxs-lookup"><span data-stu-id="95dd5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="95dd5-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="95dd5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="95dd5-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="95dd5-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="95dd5-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="95dd5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="95dd5-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="95dd5-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="95dd5-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="95dd5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="95dd5-112">`true` Se e solo se esattamente uno degli `a` e `b` è `true` .</span><span class="sxs-lookup"><span data-stu-id="95dd5-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>
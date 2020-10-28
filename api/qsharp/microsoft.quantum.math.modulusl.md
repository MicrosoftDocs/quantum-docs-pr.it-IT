---
uid: Microsoft.Quantum.Math.ModulusL
title: Funzione modulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725098"
---
# <a name="modulusl-function"></a><span data-ttu-id="ab9ac-102">Funzione modulo</span><span class="sxs-lookup"><span data-stu-id="ab9ac-102">ModulusL function</span></span>

<span data-ttu-id="ab9ac-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ab9ac-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab9ac-105">Calcola il residuo canonico del `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="ab9ac-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="ab9ac-106">Input</span><span class="sxs-lookup"><span data-stu-id="ab9ac-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="ab9ac-107">valore: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab9ac-108">Valore di cui viene calcolato il residuo</span><span class="sxs-lookup"><span data-stu-id="ab9ac-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="ab9ac-109">modulo: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab9ac-110">Il modulo in base al quale vengono presi i residui deve essere positivo</span><span class="sxs-lookup"><span data-stu-id="ab9ac-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ab9ac-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ab9ac-112">Integer $r $ tra 0 e `modulus - 1` così `value - r` divisibile per modulo</span><span class="sxs-lookup"><span data-stu-id="ab9ac-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="ab9ac-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="ab9ac-113">Remarks</span></span>

<span data-ttu-id="ab9ac-114">Questa funzione si comporta in modo diverso a seconda del comportamento dell'operatore `%` in C# e Q # come nel risultato è sempre un numero intero positivo compreso tra 0 e `modulus - 1` , anche se il valore è negativo.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>
---
uid: Microsoft.Quantum.Logical.Not
title: Not-funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709862"
---
# <a name="not-function"></a><span data-ttu-id="eab86-102">Not-funzione</span><span class="sxs-lookup"><span data-stu-id="eab86-102">Not function</span></span>

<span data-ttu-id="eab86-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eab86-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eab86-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eab86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eab86-105">Restituisce la negazione booleana di un valore.</span><span class="sxs-lookup"><span data-stu-id="eab86-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="eab86-106">Input</span><span class="sxs-lookup"><span data-stu-id="eab86-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="eab86-107">valore: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eab86-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eab86-108">Valore da negare.</span><span class="sxs-lookup"><span data-stu-id="eab86-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eab86-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eab86-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eab86-110">`true` Se e solo se `value` è `false` .</span><span class="sxs-lookup"><span data-stu-id="eab86-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eab86-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="eab86-111">Remarks</span></span>

<span data-ttu-id="eab86-112">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="eab86-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```
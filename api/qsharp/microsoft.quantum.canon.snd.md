---
uid: Microsoft.Quantum.Canon.Snd
title: SND (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852162"
---
# <a name="snd-function"></a><span data-ttu-id="b0503-102">SND (funzione)</span><span class="sxs-lookup"><span data-stu-id="b0503-102">Snd function</span></span>

<span data-ttu-id="b0503-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0503-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0503-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0503-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0503-105">Data una coppia, restituisce il secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="b0503-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="b0503-106">Input</span><span class="sxs-lookup"><span data-stu-id="b0503-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="b0503-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="b0503-107">pair : ('T,'U)</span></span>

<span data-ttu-id="b0503-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="b0503-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="b0503-109">Output:' U</span><span class="sxs-lookup"><span data-stu-id="b0503-109">Output : 'U</span></span>

<span data-ttu-id="b0503-110">Secondo elemento di `pair` .</span><span class="sxs-lookup"><span data-stu-id="b0503-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0503-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b0503-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0503-112">T</span><span class="sxs-lookup"><span data-stu-id="b0503-112">'T</span></span>

<span data-ttu-id="b0503-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="b0503-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="b0503-114">' U</span><span class="sxs-lookup"><span data-stu-id="b0503-114">'U</span></span>

<span data-ttu-id="b0503-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="b0503-115">The type of the pair's second member.</span></span>
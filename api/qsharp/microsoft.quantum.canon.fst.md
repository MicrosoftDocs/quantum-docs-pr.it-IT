---
uid: Microsoft.Quantum.Canon.Fst
title: FST (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206936"
---
# <a name="fst-function"></a><span data-ttu-id="64ef5-102">FST (funzione)</span><span class="sxs-lookup"><span data-stu-id="64ef5-102">Fst function</span></span>

<span data-ttu-id="64ef5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64ef5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64ef5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64ef5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64ef5-105">Data una coppia, restituisce il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="64ef5-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="64ef5-106">Input</span><span class="sxs-lookup"><span data-stu-id="64ef5-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="64ef5-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="64ef5-107">pair : ('T,'U)</span></span>

<span data-ttu-id="64ef5-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="64ef5-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="64ef5-109">Output:' t</span><span class="sxs-lookup"><span data-stu-id="64ef5-109">Output : 'T</span></span>

<span data-ttu-id="64ef5-110">Primo elemento di `pair`.</span><span class="sxs-lookup"><span data-stu-id="64ef5-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64ef5-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="64ef5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64ef5-112">T</span><span class="sxs-lookup"><span data-stu-id="64ef5-112">'T</span></span>

<span data-ttu-id="64ef5-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="64ef5-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="64ef5-114">' U</span><span class="sxs-lookup"><span data-stu-id="64ef5-114">'U</span></span>

<span data-ttu-id="64ef5-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="64ef5-115">The type of the pair's second member.</span></span>
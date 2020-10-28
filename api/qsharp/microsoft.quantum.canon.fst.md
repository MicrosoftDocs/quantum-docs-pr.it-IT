---
uid: Microsoft.Quantum.Canon.Fst
title: FST (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716187"
---
# <a name="fst-function"></a><span data-ttu-id="a95f2-102">FST (funzione)</span><span class="sxs-lookup"><span data-stu-id="a95f2-102">Fst function</span></span>

<span data-ttu-id="a95f2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a95f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a95f2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a95f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a95f2-105">Data una coppia, restituisce il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="a95f2-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="a95f2-106">Input</span><span class="sxs-lookup"><span data-stu-id="a95f2-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="a95f2-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="a95f2-107">pair : ('T,'U)</span></span>

<span data-ttu-id="a95f2-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="a95f2-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="a95f2-109">Output:' t</span><span class="sxs-lookup"><span data-stu-id="a95f2-109">Output : 'T</span></span>

<span data-ttu-id="a95f2-110">Primo elemento di `pair`.</span><span class="sxs-lookup"><span data-stu-id="a95f2-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a95f2-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a95f2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a95f2-112">T</span><span class="sxs-lookup"><span data-stu-id="a95f2-112">'T</span></span>

<span data-ttu-id="a95f2-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="a95f2-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="a95f2-114">' U</span><span class="sxs-lookup"><span data-stu-id="a95f2-114">'U</span></span>

<span data-ttu-id="a95f2-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="a95f2-115">The type of the pair's second member.</span></span>
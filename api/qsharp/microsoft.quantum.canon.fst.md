---
uid: Microsoft.Quantum.Canon.Fst
title: FST (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840508"
---
# <a name="fst-function"></a><span data-ttu-id="56748-102">FST (funzione)</span><span class="sxs-lookup"><span data-stu-id="56748-102">Fst function</span></span>

<span data-ttu-id="56748-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56748-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56748-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56748-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56748-105">Data una coppia, restituisce il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="56748-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="56748-106">Input</span><span class="sxs-lookup"><span data-stu-id="56748-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="56748-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="56748-107">pair : ('T,'U)</span></span>

<span data-ttu-id="56748-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="56748-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="56748-109">Output:' t</span><span class="sxs-lookup"><span data-stu-id="56748-109">Output : 'T</span></span>

<span data-ttu-id="56748-110">Primo elemento di `pair`.</span><span class="sxs-lookup"><span data-stu-id="56748-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="56748-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="56748-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56748-112">T</span><span class="sxs-lookup"><span data-stu-id="56748-112">'T</span></span>

<span data-ttu-id="56748-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="56748-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="56748-114">' U</span><span class="sxs-lookup"><span data-stu-id="56748-114">'U</span></span>

<span data-ttu-id="56748-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="56748-115">The type of the pair's second member.</span></span>
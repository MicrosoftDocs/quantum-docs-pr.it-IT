---
uid: Microsoft.Quantum.Canon.Snd
title: SND (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205321"
---
# <a name="snd-function"></a><span data-ttu-id="0042a-102">SND (funzione)</span><span class="sxs-lookup"><span data-stu-id="0042a-102">Snd function</span></span>

<span data-ttu-id="0042a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0042a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0042a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0042a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0042a-105">Data una coppia, restituisce il secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="0042a-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="0042a-106">Input</span><span class="sxs-lookup"><span data-stu-id="0042a-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="0042a-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="0042a-107">pair : ('T,'U)</span></span>

<span data-ttu-id="0042a-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="0042a-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="0042a-109">Output:' U</span><span class="sxs-lookup"><span data-stu-id="0042a-109">Output : 'U</span></span>

<span data-ttu-id="0042a-110">Secondo elemento di `pair` .</span><span class="sxs-lookup"><span data-stu-id="0042a-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0042a-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0042a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0042a-112">T</span><span class="sxs-lookup"><span data-stu-id="0042a-112">'T</span></span>

<span data-ttu-id="0042a-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="0042a-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="0042a-114">' U</span><span class="sxs-lookup"><span data-stu-id="0042a-114">'U</span></span>

<span data-ttu-id="0042a-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="0042a-115">The type of the pair's second member.</span></span>
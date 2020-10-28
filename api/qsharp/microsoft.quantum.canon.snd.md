---
uid: Microsoft.Quantum.Canon.Snd
title: SND (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715448"
---
# <a name="snd-function"></a><span data-ttu-id="92f8a-102">SND (funzione)</span><span class="sxs-lookup"><span data-stu-id="92f8a-102">Snd function</span></span>

<span data-ttu-id="92f8a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92f8a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92f8a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92f8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92f8a-105">Data una coppia, restituisce il secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="92f8a-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="92f8a-106">Input</span><span class="sxs-lookup"><span data-stu-id="92f8a-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="92f8a-107">coppia: (t,' U)</span><span class="sxs-lookup"><span data-stu-id="92f8a-107">pair : ('T,'U)</span></span>

<span data-ttu-id="92f8a-108">Tupla con due elementi.</span><span class="sxs-lookup"><span data-stu-id="92f8a-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="92f8a-109">Output:' U</span><span class="sxs-lookup"><span data-stu-id="92f8a-109">Output : 'U</span></span>

<span data-ttu-id="92f8a-110">Secondo elemento di `pair` .</span><span class="sxs-lookup"><span data-stu-id="92f8a-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="92f8a-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="92f8a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="92f8a-112">T</span><span class="sxs-lookup"><span data-stu-id="92f8a-112">'T</span></span>

<span data-ttu-id="92f8a-113">Tipo del primo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="92f8a-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="92f8a-114">' U</span><span class="sxs-lookup"><span data-stu-id="92f8a-114">'U</span></span>

<span data-ttu-id="92f8a-115">Tipo del secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="92f8a-115">The type of the pair's second member.</span></span>
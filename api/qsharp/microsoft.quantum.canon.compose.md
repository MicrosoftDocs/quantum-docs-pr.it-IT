---
uid: Microsoft.Quantum.Canon.Compose
title: Compose (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840898"
---
# <a name="compose-function"></a><span data-ttu-id="58fb6-102">Compose (funzione)</span><span class="sxs-lookup"><span data-stu-id="58fb6-102">Compose function</span></span>

<span data-ttu-id="58fb6-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58fb6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58fb6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58fb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58fb6-105">Restituisce la composizione di due funzioni.</span><span class="sxs-lookup"><span data-stu-id="58fb6-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="58fb6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58fb6-106">Description</span></span>

<span data-ttu-id="58fb6-107">Date due funzioni $f $ e $g $, restituisce una nuova funzione che rappresenta $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="58fb6-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="58fb6-108">Input</span><span class="sxs-lookup"><span data-stu-id="58fb6-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="58fb6-109">Outer:' U->' V</span><span class="sxs-lookup"><span data-stu-id="58fb6-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="58fb6-110">Seconda funzione da applicare.</span><span class="sxs-lookup"><span data-stu-id="58fb6-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="58fb6-111">Inner: t->' U</span><span class="sxs-lookup"><span data-stu-id="58fb6-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="58fb6-112">Prima funzione da applicare.</span><span class="sxs-lookup"><span data-stu-id="58fb6-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="58fb6-113">Output:' t->' V</span><span class="sxs-lookup"><span data-stu-id="58fb6-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="58fb6-114">Una nuova funzione $h $ tale che per tutti gli input $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="58fb6-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58fb6-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="58fb6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58fb6-116">T</span><span class="sxs-lookup"><span data-stu-id="58fb6-116">'T</span></span>

<span data-ttu-id="58fb6-117">Tipo di input della prima funzione da applicare.</span><span class="sxs-lookup"><span data-stu-id="58fb6-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="58fb6-118">' U</span><span class="sxs-lookup"><span data-stu-id="58fb6-118">'U</span></span>

<span data-ttu-id="58fb6-119">Il tipo di output della prima funzione da applicare e il tipo di input della seconda funzione da applicare.</span><span class="sxs-lookup"><span data-stu-id="58fb6-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="58fb6-120">' V</span><span class="sxs-lookup"><span data-stu-id="58fb6-120">'V</span></span>

<span data-ttu-id="58fb6-121">Tipo di output della seconda funzione da applicare.</span><span class="sxs-lookup"><span data-stu-id="58fb6-121">The output type of the second function to be applied.</span></span>
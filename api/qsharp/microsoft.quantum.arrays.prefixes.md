---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funzione Prefixes
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718938"
---
# <a name="prefixes-function"></a><span data-ttu-id="bb76b-102">Funzione Prefixes</span><span class="sxs-lookup"><span data-stu-id="bb76b-102">Prefixes function</span></span>

<span data-ttu-id="bb76b-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bb76b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bb76b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb76b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb76b-105">Data una matrice, restituisce tutti i relativi prefissi.</span><span class="sxs-lookup"><span data-stu-id="bb76b-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="bb76b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb76b-106">Description</span></span>

<span data-ttu-id="bb76b-107">Restituisce una matrice di tutti i prefissi, a partire da una matrice che contiene solo il primo elemento fino alla matrice completa.</span><span class="sxs-lookup"><span data-stu-id="bb76b-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="bb76b-108">Input</span><span class="sxs-lookup"><span data-stu-id="bb76b-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bb76b-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="bb76b-109">array : 'T[]</span></span>

<span data-ttu-id="bb76b-110">Matrice di elementi.</span><span class="sxs-lookup"><span data-stu-id="bb76b-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="bb76b-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="bb76b-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bb76b-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bb76b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb76b-113">T</span><span class="sxs-lookup"><span data-stu-id="bb76b-113">'T</span></span>

<span data-ttu-id="bb76b-114">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="bb76b-114">The type of `array` elements.</span></span>
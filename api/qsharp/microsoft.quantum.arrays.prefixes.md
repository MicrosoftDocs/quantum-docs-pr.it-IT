---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funzione Prefixes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220390"
---
# <a name="prefixes-function"></a><span data-ttu-id="6e655-102">Funzione Prefixes</span><span class="sxs-lookup"><span data-stu-id="6e655-102">Prefixes function</span></span>

<span data-ttu-id="6e655-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6e655-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6e655-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e655-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e655-105">Data una matrice, restituisce tutti i relativi prefissi.</span><span class="sxs-lookup"><span data-stu-id="6e655-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="6e655-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e655-106">Description</span></span>

<span data-ttu-id="6e655-107">Restituisce una matrice di tutti i prefissi, a partire da una matrice che contiene solo il primo elemento fino alla matrice completa.</span><span class="sxs-lookup"><span data-stu-id="6e655-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="6e655-108">Input</span><span class="sxs-lookup"><span data-stu-id="6e655-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="6e655-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="6e655-109">array : 'T[]</span></span>

<span data-ttu-id="6e655-110">Matrice di elementi.</span><span class="sxs-lookup"><span data-stu-id="6e655-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6e655-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="6e655-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6e655-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6e655-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6e655-113">T</span><span class="sxs-lookup"><span data-stu-id="6e655-113">'T</span></span>

<span data-ttu-id="6e655-114">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="6e655-114">The type of `array` elements.</span></span>
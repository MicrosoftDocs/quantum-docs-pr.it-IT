---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funzione Prefixes
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845519"
---
# <a name="prefixes-function"></a><span data-ttu-id="42919-102">Funzione Prefixes</span><span class="sxs-lookup"><span data-stu-id="42919-102">Prefixes function</span></span>

<span data-ttu-id="42919-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="42919-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="42919-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42919-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42919-105">Data una matrice, restituisce tutti i relativi prefissi.</span><span class="sxs-lookup"><span data-stu-id="42919-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="42919-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42919-106">Description</span></span>

<span data-ttu-id="42919-107">Restituisce una matrice di tutti i prefissi, a partire da una matrice che contiene solo il primo elemento fino alla matrice completa.</span><span class="sxs-lookup"><span data-stu-id="42919-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="42919-108">Input</span><span class="sxs-lookup"><span data-stu-id="42919-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="42919-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="42919-109">array : 'T[]</span></span>

<span data-ttu-id="42919-110">Matrice di elementi.</span><span class="sxs-lookup"><span data-stu-id="42919-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="42919-111">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="42919-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42919-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="42919-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42919-113">T</span><span class="sxs-lookup"><span data-stu-id="42919-113">'T</span></span>

<span data-ttu-id="42919-114">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="42919-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="42919-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="42919-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```
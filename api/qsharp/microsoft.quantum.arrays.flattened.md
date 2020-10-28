---
uid: Microsoft.Quantum.Arrays.Flattened
title: Funzione Flat
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719238"
---
# <a name="flattened-function"></a><span data-ttu-id="db142-102">Funzione Flat</span><span class="sxs-lookup"><span data-stu-id="db142-102">Flattened function</span></span>

<span data-ttu-id="db142-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db142-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db142-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db142-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db142-105">Data una matrice di matrici, restituisce la concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="db142-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="db142-106">Input</span><span class="sxs-lookup"><span data-stu-id="db142-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="db142-107">matrici:' t [] []</span><span class="sxs-lookup"><span data-stu-id="db142-107">arrays : 'T[][]</span></span>

<span data-ttu-id="db142-108">Matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="db142-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="db142-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="db142-109">Output : 'T[]</span></span>

<span data-ttu-id="db142-110">Concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="db142-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db142-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="db142-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db142-112">T</span><span class="sxs-lookup"><span data-stu-id="db142-112">'T</span></span>

<span data-ttu-id="db142-113">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="db142-113">The type of `array` elements.</span></span>
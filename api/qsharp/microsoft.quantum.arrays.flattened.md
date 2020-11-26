---
uid: Microsoft.Quantum.Arrays.Flattened
title: Funzione Flat
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221216"
---
# <a name="flattened-function"></a><span data-ttu-id="479f0-102">Funzione Flat</span><span class="sxs-lookup"><span data-stu-id="479f0-102">Flattened function</span></span>

<span data-ttu-id="479f0-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="479f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="479f0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="479f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="479f0-105">Data una matrice di matrici, restituisce la concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="479f0-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="479f0-106">Input</span><span class="sxs-lookup"><span data-stu-id="479f0-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="479f0-107">matrici:' t [] []</span><span class="sxs-lookup"><span data-stu-id="479f0-107">arrays : 'T[][]</span></span>

<span data-ttu-id="479f0-108">Matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="479f0-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="479f0-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="479f0-109">Output : 'T[]</span></span>

<span data-ttu-id="479f0-110">Concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="479f0-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="479f0-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="479f0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="479f0-112">T</span><span class="sxs-lookup"><span data-stu-id="479f0-112">'T</span></span>

<span data-ttu-id="479f0-113">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="479f0-113">The type of `array` elements.</span></span>
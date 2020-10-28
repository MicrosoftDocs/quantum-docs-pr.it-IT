---
uid: Microsoft.Quantum.Arrays.Padded
title: Funzione riempita
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718983"
---
# <a name="padded-function"></a><span data-ttu-id="0b260-102">Funzione riempita</span><span class="sxs-lookup"><span data-stu-id="0b260-102">Padded function</span></span>

<span data-ttu-id="0b260-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b260-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b260-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b260-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b260-105">Restituisce una matrice riempita con i valori specificati fino a una lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="0b260-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0b260-106">Input</span><span class="sxs-lookup"><span data-stu-id="0b260-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="0b260-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b260-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b260-108">Lunghezza della matrice riempita.</span><span class="sxs-lookup"><span data-stu-id="0b260-108">The length of the padded array.</span></span> <span data-ttu-id="0b260-109">Se questo è positivo, `inputArray` viene riempito alla testa.</span><span class="sxs-lookup"><span data-stu-id="0b260-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="0b260-110">Se si tratta di un valore negativo, `inputArray` viene riempito alla fine della coda.</span><span class="sxs-lookup"><span data-stu-id="0b260-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="0b260-111">impostazione predefinita:' t</span><span class="sxs-lookup"><span data-stu-id="0b260-111">defaultElement : 'T</span></span>

<span data-ttu-id="0b260-112">Valore predefinito da usare per gli elementi di riempimento.</span><span class="sxs-lookup"><span data-stu-id="0b260-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="0b260-113">inputArray:' t []</span><span class="sxs-lookup"><span data-stu-id="0b260-113">inputArray : 'T[]</span></span>

<span data-ttu-id="0b260-114">Matrice i cui valori si trovano all'inizio della matrice di output.</span><span class="sxs-lookup"><span data-stu-id="0b260-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="0b260-115">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="0b260-115">Output : 'T[]</span></span>

<span data-ttu-id="0b260-116">Matrice `output` `inputArray` riempita all'inizio con `defaultElement` s finché non `output` ha lunghezza `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="0b260-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b260-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0b260-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b260-118">T</span><span class="sxs-lookup"><span data-stu-id="0b260-118">'T</span></span>

<span data-ttu-id="0b260-119">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="0b260-119">The type of the array elements.</span></span>
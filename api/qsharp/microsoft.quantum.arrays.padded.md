---
uid: Microsoft.Quantum.Arrays.Padded
title: Funzione riempita
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845555"
---
# <a name="padded-function"></a><span data-ttu-id="9452a-102">Funzione riempita</span><span class="sxs-lookup"><span data-stu-id="9452a-102">Padded function</span></span>

<span data-ttu-id="9452a-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9452a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9452a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9452a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9452a-105">Restituisce una matrice riempita con i valori specificati fino a una lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="9452a-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9452a-106">Input</span><span class="sxs-lookup"><span data-stu-id="9452a-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="9452a-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9452a-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9452a-108">Lunghezza della matrice riempita.</span><span class="sxs-lookup"><span data-stu-id="9452a-108">The length of the padded array.</span></span> <span data-ttu-id="9452a-109">Se questo è positivo, `inputArray` viene riempito alla testa.</span><span class="sxs-lookup"><span data-stu-id="9452a-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="9452a-110">Se si tratta di un valore negativo, `inputArray` viene riempito alla fine della coda.</span><span class="sxs-lookup"><span data-stu-id="9452a-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="9452a-111">impostazione predefinita:' t</span><span class="sxs-lookup"><span data-stu-id="9452a-111">defaultElement : 'T</span></span>

<span data-ttu-id="9452a-112">Valore predefinito da usare per gli elementi di riempimento.</span><span class="sxs-lookup"><span data-stu-id="9452a-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="9452a-113">inputArray:' t []</span><span class="sxs-lookup"><span data-stu-id="9452a-113">inputArray : 'T[]</span></span>

<span data-ttu-id="9452a-114">Matrice i cui valori si trovano all'inizio della matrice di output.</span><span class="sxs-lookup"><span data-stu-id="9452a-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="9452a-115">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="9452a-115">Output : 'T[]</span></span>

<span data-ttu-id="9452a-116">Matrice `output` `inputArray` riempita all'inizio con `defaultElement` s finché non `output` ha lunghezza `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="9452a-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9452a-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9452a-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9452a-118">T</span><span class="sxs-lookup"><span data-stu-id="9452a-118">'T</span></span>

<span data-ttu-id="9452a-119">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="9452a-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="9452a-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="9452a-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```
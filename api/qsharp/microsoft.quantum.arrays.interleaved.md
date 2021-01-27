---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848105"
---
# <a name="interleaved-function"></a><span data-ttu-id="9124c-102">Funzione Interleaved</span><span class="sxs-lookup"><span data-stu-id="9124c-102">Interleaved function</span></span>

<span data-ttu-id="9124c-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9124c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9124c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9124c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9124c-105">Interleaves due matrici di (quasi) stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9124c-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="9124c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9124c-106">Description</span></span>

<span data-ttu-id="9124c-107">Questa funzione restituisce l'interfoliazione di due matrici, a partire dal primo elemento della prima matrice, dal primo elemento della seconda matrice e così via.</span><span class="sxs-lookup"><span data-stu-id="9124c-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="9124c-108">La prima matrice deve avere la stessa lunghezza del secondo oppure può avere un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="9124c-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="9124c-109">Input</span><span class="sxs-lookup"><span data-stu-id="9124c-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="9124c-110">primo:' t []</span><span class="sxs-lookup"><span data-stu-id="9124c-110">first : 'T[]</span></span>

<span data-ttu-id="9124c-111">Prima matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="9124c-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="9124c-112">secondo:' t []</span><span class="sxs-lookup"><span data-stu-id="9124c-112">second : 'T[]</span></span>

<span data-ttu-id="9124c-113">Seconda matrice da Interleave.</span><span class="sxs-lookup"><span data-stu-id="9124c-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="9124c-114">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="9124c-114">Output : 'T[]</span></span>

<span data-ttu-id="9124c-115">Matrice Interleaved</span><span class="sxs-lookup"><span data-stu-id="9124c-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9124c-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9124c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9124c-117">T</span><span class="sxs-lookup"><span data-stu-id="9124c-117">'T</span></span>

<span data-ttu-id="9124c-118">Tipo di ogni elemento di `first` e `second` .</span><span class="sxs-lookup"><span data-stu-id="9124c-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="9124c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9124c-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```